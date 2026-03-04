package ru.sberbank.uvz3.pledges.domain;

import jakarta.persistence.*;
import lombok.AccessLevel;
import lombok.Getter;
import lombok.NoArgsConstructor;
import lombok.Setter;
import org.hibernate.annotations.CreationTimestamp;
import org.hibernate.annotations.SortNatural;

import java.time.Instant;
import java.util.SortedSet;
import java.util.TreeSet;

@Entity
@Setter
@Getter
@Table(name = "lot", indexes = {
        @Index(name = "idx_client_id", columnList = "client_id"),
        @Index(name = "idx_origin_id", columnList = "origin_id"),
})
@Inheritance
@NoArgsConstructor
@DiscriminatorColumn(name = "lot_type")
public class CommonLot<T> {

    @Id
    @SequenceGenerator(name = "LOT_SEQUENCE", sequenceName = "LOT_SEQUENCE")
    @GeneratedValue(strategy = GenerationType.SEQUENCE, generator = "LOT_SEQUENCE")
    Long id;
    @Version
    @Column(name = "version")
    Long version;
    @Column(name = "name")
    String name;
    @Column(name = "initiator")
    String initiator;
    @CreationTimestamp
    @Column(name = "created_at", nullable = false, updatable = false)
    Instant createdAt;

    @Column(name = "client_id")
    String clientId;

    @Column(name = "origin_id")
    String originId;
    @Column(name = "origin_type")
    @Enumerated(EnumType.STRING)
    LotOriginType originType;

    @Setter(AccessLevel.NONE)
    @SortNatural
    @OneToMany(fetch = FetchType.LAZY, cascade = CascadeType.REMOVE, orphanRemoval = true, mappedBy = "lot")
    SortedSet<T> pledges = new TreeSet<>();

    public CommonLot(String clientId, String originId, LotOriginType originType, String initiator) {
        this.clientId = clientId;
        this.originId = originId;
        this.originType = originType;
        this.initiator = initiator;
    }
}
