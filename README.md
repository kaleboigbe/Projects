## Food Time

    create database food_time;
    use food_time;

    SELECT *
    FROM food_time
    LIMIT 10;

    SELECT COUNT(*) AS High_traffic_level
    FROM food_time
    WHERE traffic_level = 'high';

    SELECT COUNT(*) AS Low_traffic_level
    FROM food_time
    WHERE traffic_level = 'low';

    SELECT DISTINCT weather_description
    FROM food_time;

    SELECT DISTINCT type_of_vehicle
    FROM food_time;

    SELECT type_of_order, COUNT(*) AS Total
    FROM food_time
    GROUP BY type_of_order;

    SELECT type_of_vehicle, COUNT(*) AS Total
    FROM food_time
    GROUP BY type_of_vehicle
    ORDER BY total DESC;

    SELECT type_of_vehicle, AVG(distance) AS avg_distance_km
    FROM food_time
    GROUP BY type_of_vehicle
    ORDER BY avg_distance_km DESC;

    SELECT traffic_level, AVG(distance) AS avg_distance_km
    FROM food_time
    GROUP BY traffic_level;

    SELECT DISTINCT delivery_person_id, COUNT(*) AS delivery_count
    FROM food_time
    GROUP BY delivery_person_id
    ORDER BY delivery_count DESC;

    SELECT weather_description, COUNT(*) AS delivery_count
    FROM food_time
    GROUP BY weather_description
    ORDER BY delivery_count DESC;

    SELECT delivery_person_age, COUNT(*) delivery_count
    FROM food_time
    GROUP BY delivery_person_age
    ORDER BY delivery_person_age ASC;

    SELECT delivery_person_age, COUNT(*) delivery_count
    FROM food_time
    GROUP BY delivery_person_age
    HAVING delivery_person_age < 35
    ORDER BY delivery_person_age ASC;

    SELECT type_of_order, AVG(target) AS avg_delivery_time
    FROM food_time
    GROUP BY type_of_order;

    SELECT ID, weather_description, type_of_order, type_of_vehicle, distance, delivery_person_ratings, traffic_level
    FROM food_time
    WHERE distance > 20 AND delivery_person_ratings < 4
    ORDER BY delivery_person_ratings DESC;

    SELECT
    CASE
    WHEN delivery_person_age < 25 THEN 'under 25'
    WHEN delivery_person_age BETWEEN 25 AND 35 THEN '25-35'
    WHEN delivery_person_age > 35 THEN 'above 35'
    END AS age_group,
    COUNT(*) AS number_of_deliveries
    FROM food_time
    GROUP BY age_group
    ORDER BY number_of_deliveries ASC;

