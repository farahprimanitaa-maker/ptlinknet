---section 1.1---
WITH itungan AS (
    SELECT
        a.region,
        COUNT(DISTINCT CASE 
            WHEN b.status = 'ACTIVE' THEN b.homeid 
        END) AS activesubscount,
        COUNT(DISTINCT a.homeid) AS homepasscount
    FROM homepass_fin a
    LEFT JOIN subscription_snapshot_fin b
        ON a.homeid = b.homeid
    GROUP BY a.region
)

SELECT
    region,
    activesubscount,
    homepasscount,
    activesubscount * 1.0 / NULLIF(homepasscount, 0) AS penetration_rate
FROM itungan;

---section 1.2---
WITH itungan AS (
    SELECT
        a.technology,
        COUNT(DISTINCT CASE 
            WHEN b.status = 'ACTIVE' THEN b.homeid 
        END) AS activesubscount,
        COUNT(DISTINCT a.homeid) AS homepasscount
    FROM homepass_fin a
    LEFT JOIN subscription_snapshot_fin b
        ON a.homeid = b.homeid
    GROUP BY a.technology
)

SELECT
    technology,
    activesubscount,
    homepasscount,
    activesubscount * 1.0 / NULLIF(homepasscount, 0) AS penetration_rate
FROM itungan;

---section 1.3---
WITH itungan AS (
    SELECT
        a.exclusive_flag,
        COUNT(DISTINCT CASE 
            WHEN b.status = 'ACTIVE' THEN b.homeid 
        END) AS activesubscount,
        COUNT(DISTINCT a.homeid) AS homepasscount
    FROM homepass_fin a
    LEFT JOIN subscription_snapshot_fin b
        ON a.homeid = b.homeid
    GROUP BY a.technology
)

SELECT
    exclusive_flag,
    activesubscount,
    homepasscount,
    activesubscount * 1.0 / NULLIF(homepasscount, 0) AS penetration_rate
FROM itungan;
