package ru.sberbank.uvz3.client.event.support

import com.zaxxer.hikari.pool.HikariProxyConnection
import org.dbunit.database.DatabaseConfig
import org.dbunit.database.DatabaseDataSourceConnection
import org.dbunit.ext.h2.H2DataTypeFactory
import org.dbunit.ext.postgresql.PostgresqlDataTypeFactory
import org.springframework.boot.autoconfigure.condition.ConditionalOnProperty
import org.springframework.context.annotation.Bean
import org.springframework.context.annotation.Configuration
import java.sql.Connection
import javax.sql.DataSource

@Configuration
class DbUnitConfiguration(
    private val dataSource: DataSource
) {

    @Bean("dbUnitDatabaseConnection")
    @ConditionalOnProperty("spring.sql.init.platform", havingValue = "h2", matchIfMissing = false)
    fun h2DataSourceConnection(): DatabaseDataSourceConnection {
        return H2DatabaseConnection(dataSource)
    }

    @Bean("dbUnitDatabaseConnection")
    @ConditionalOnProperty("spring.sql.init.platform", havingValue = "postgres", matchIfMissing = true)
    fun postgresDataSourceConnection(): DatabaseDataSourceConnection {
        return PostgresqlDatabaseConnection(dataSource)
    }

    open class DbUnitDatabaseConnection(dataSource: DataSource) : DatabaseDataSourceConnection(dataSource) {
        override fun getConnection(): Connection {
            val conn = super.getConnection()

            return if (conn is HikariProxyConnection) {
                // to avoid ClassCastException in Oracle
                conn.unwrap(Connection::class.java)
            } else {
                conn
            }
        }
    }

    class H2DatabaseConnection(dataSource: DataSource) : DbUnitDatabaseConnection(dataSource) {
        override fun getConfig(): DatabaseConfig {
            val config = super.getConfig()
            config.setProperty(DatabaseConfig.PROPERTY_DATATYPE_FACTORY, H2DataTypeFactory())
            return config
        }
    }

    class PostgresqlDatabaseConnection(dataSource: DataSource) : DbUnitDatabaseConnection(dataSource) {
        override fun getConfig(): DatabaseConfig {
            val config = super.getConfig()
            config.setProperty(DatabaseConfig.PROPERTY_DATATYPE_FACTORY, PostgresqlDataTypeFactory())
            return config
        }
    }
}
