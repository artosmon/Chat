# Chat

> Task :client-events:test

PublishDebtEqualZeroChangedEventsServiceTest > data for events exists but amount above its limit() FAILED
    java.lang.IllegalStateException at DefaultCacheAwareContextLoaderDelegate.java:195
        Caused by: java.lang.IllegalStateException at ConfigurationClassBeanDefinitionReader.java:172
            Caused by: java.lang.IllegalArgumentException at ClassUtils.java:353
                Caused by: java.lang.ClassNotFoundException at BuiltinClassLoader.java:641

PublishDebtEqualZeroChangedEventsServiceTest > launch first time() FAILED
        Caused by: java.lang.IllegalStateException at ConfigurationClassBeanDefinitionReader.java:172

    java.lang.IllegalStateException at DefaultCacheAwareContextLoaderDelegate.java:157
            Caused by: java.lang.IllegalArgumentException at ClassUtils.java:353


                Caused by: java.lang.ClassNotFoundException at BuiltinClassLoader.java:641

PublishDebtEqualZeroChangedEventsServiceTest > data for events does not exist() FAILED
    java.lang.IllegalStateException at DefaultCacheAwareContextLoaderDelegate.java:157

PublishDebtEqualZeroChangedEventsServiceTest > data for events exists() FAILED
    java.lang.IllegalStateException at DefaultCacheAwareContextLoaderDelegate.java:157

PublishStateOfBalanceChangedEventsServiceTest > launch first time() FAILED
    java.lang.IllegalStateException at DefaultCacheAwareContextLoaderDelegate.java:157

PublishStateOfBalanceChangedEventsServiceTest > data for events does not exist() FAILED
    java.lang.IllegalStateException at DefaultCacheAwareContextLoaderDelegate.java:157

PublishStateOfBalanceChangedEventsServiceTest > data for events exists() FAILED
    java.lang.IllegalStateException at DefaultCacheAwareContextLoaderDelegate.java:157

PublishClientMvkdResultEventsCommonTest > no data for mvkd event, model name is not mvkd_ksb_red() FAILED
    java.lang.IllegalStateException at DefaultCacheAwareContextLoaderDelegate.java:195
        Caused by: java.lang.IllegalStateException at ConfigurationClassBeanDefinitionReader.java:172
        Caused by: java.lang.IllegalStateException at ConfigurationClassBeanDefinitionReader.java:172

            Caused by: java.lang.IllegalArgumentException at ClassUtils.java:353
            Caused by: java.lang.IllegalArgumentException at ClassUtils.java:353

                Caused by: java.lang.ClassNotFoundException at BuiltinClassLoader.java:641
                Caused by: java.lang.ClassNotFoundException at BuiltinClassLoader.java:641


PublishClientMvkdResultEventsCommonTest > launch first time mvkd event() FAILED
    java.lang.IllegalStateException at DefaultCacheAwareContextLoaderDelegate.java:157

PublishClientMvkdResultEventsWithNoPeriodDateServiceTest > Данные для публикации МВКД результата есть, period_date = null, сегодня 7 июня() FAILED
    java.lang.IllegalStateException at DefaultCacheAwareContextLoaderDelegate.java:157

PublishClientMvkdResultEventsWithNoPeriodDateServiceTest > Данные для публикации МВКД результата есть, period_date = null, сегодня 7 мая() FAILED
    java.lang.IllegalStateException at DefaultCacheAwareContextLoaderDelegate.java:157

PublishClientMvkdResultEventsWithNoPeriodDateServiceTest > Данные для публикации МВКД результата есть, period_date = null, сегодня 7 декабря() FAILED
    java.lang.IllegalStateException at DefaultCacheAwareContextLoaderDelegate.java:157

PublishClientMvkdResultEventsWithNoPeriodDateServiceTest > Данные для публикации МВКД результата есть, period_date!= null, сегодня 7 сентября() FAILED
    java.lang.IllegalStateException at DefaultCacheAwareContextLoaderDelegate.java:157

PublishClientMvkdResultEventsWithNoPeriodDateServiceTest > Данных для публикации МВКД результата нет, period_date = null, сегодня 8 декабря() FAILED
    java.lang.IllegalStateException at DefaultCacheAwareContextLoaderDelegate.java:157

PublishClientMvkdResultEventsWithPeriodDateServiceTest > Данные для публикации МВКД результата есть, period_date != null, записи на пограничных датах + запись на квартал позже() FAILED
    java.lang.IllegalStateException at DefaultCacheAwareContextLoaderDelegate.java:157

PublishClientMvkdResultEventsWithPeriodDateServiceTest > Данные для публикации МВКД результата есть, period_date != null, 2 квартал() FAILED
    java.lang.IllegalStateException at DefaultCacheAwareContextLoaderDelegate.java:157

PublishClientMvkdResultEventsWithPeriodDateServiceTest > Данные для публикации МВКД результата есть, period_date != null, 4 квартал() FAILED
    java.lang.IllegalStateException at DefaultCacheAwareContextLoaderDelegate.java:157

PublishClientMvkdResultEventsWithPeriodDateServiceTest > Данные для публикации отсутствуют, period_date != null, несколько кварталов() FAILED
    java.lang.IllegalStateException at DefaultCacheAwareContextLoaderDelegate.java:157

PublishClientMvkdResultEventsWithPeriodDateServiceTest > Данные для публикации МВКД результата есть, period_date != null, 1 квартал() FAILED
    java.lang.IllegalStateException at DefaultCacheAwareContextLoaderDelegate.java:157

PublishClientMvkdResultEventsWithPeriodDateServiceTest > Данные для публикации МВКД результата есть, period_date != null, все кварталы() FAILED
    java.lang.IllegalStateException at DefaultCacheAwareContextLoaderDelegate.java:157

PublishClientMvkdResultEventsWithPeriodDateServiceTest > Данные для публикации МВКД результата есть, period_date != null, 3 квартал() FAILED
    java.lang.IllegalStateException at DefaultCacheAwareContextLoaderDelegate.java:157

DefaultCurrentDateProviderTest > CurrentDataProvider возвращает текущую дату() FAILED
    java.lang.IllegalStateException at DefaultCacheAwareContextLoaderDelegate.java:195
        Caused by: java.lang.IllegalStateException at ConfigurationClassBeanDefinitionReader.java:172
        Caused by: java.lang.IllegalStateException at ConfigurationClassBeanDefinitionReader.java:172

            Caused by: java.lang.IllegalArgumentException at ClassUtils.java:353
            Caused by: java.lang.IllegalArgumentException at ClassUtils.java:353

                Caused by: java.lang.ClassNotFoundException at BuiltinClassLoader.java:641
                Caused by: java.lang.ClassNotFoundException at BuiltinClassLoader.java:641


EventCountCheckerTest > Чекер вернул isValidationSuccessful = false() FAILED
    java.lang.IllegalStateException at DefaultCacheAwareContextLoaderDelegate.java:157

EventCountCheckerTest > Чекер вернул isValidationSuccessful = true() FAILED
    java.lang.IllegalStateException at DefaultCacheAwareContextLoaderDelegate.java:157

MockCurrentDataProviderTest > CurrentDataProvider возвращает 2022-04-18() FAILED
    java.lang.IllegalStateException at DefaultCacheAwareContextLoaderDelegate.java:195
        Caused by: java.lang.IllegalStateException at ConfigurationClassBeanDefinitionReader.java:172
        Caused by: java.lang.IllegalStateException at ConfigurationClassBeanDefinitionReader.java:172

            Caused by: java.lang.IllegalArgumentException at ClassUtils.java:353
            Caused by: java.lang.IllegalArgumentException at ClassUtils.java:353

                Caused by: java.lang.ClassNotFoundException at BuiltinClassLoader.java:641
                Caused by: java.lang.ClassNotFoundException at BuiltinClassLoader.java:641


TaskFactoryTest > newEventLimitExceedTask создал задачу() FAILED
    java.lang.IllegalStateException at DefaultCacheAwareContextLoaderDelegate.java:157

26 tests completed, 26 failed

> Task :client-events:test FAILED

[Incubating] Problems report is available at: file:///C:/Work/uvz/client-events/build/reports/problems/problems-report.html

Execution failed for task ':client-events:test'.
> There were failing tests. See the report at: file:///C:/Work/uvz/client-events/client-events/build/reports/tests/test/index.html

* Try:
> Run with --scan to generate a Build Scan (powered by Develocity).
Deprecated Gradle features were used in this build, making it incompatible with Gradle 10.
You can use '--warning-mode all' to show the individual deprecation warnings and determine if they come from your own scripts or plugins.
For more on this, please refer to https://docs.gradle.org/9.2.1/userguide/command_line_interface.html#sec:command_line_warnings in the Gradle documentation.
BUILD FAILED in 29s
14 actionable tasks: 6 executed, 8 up-to-date


