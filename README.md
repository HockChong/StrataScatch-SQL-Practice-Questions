# StrataScatch-SQL-Practice-Questions

# PostgreSQL Practice Question

Classify each business as a restaurant, cafe, school, or other. A restaurant should have the word 'restaurant' in the business name. For cafes, 'cafe', 'café', or 'coffee' can be in the business name. 'School' should be in the business name for schools. All other businesses should be classified as 'other'. Output the business name and the calculated classification.

✨ CASE + wildcard "ILIKE" + array

✨ ILIKE is not case sensitive, make use array to make our SQL script
more organized and readable

'''SQL
SELECT distinct business_name,
       CASE
           WHEN business_name ILIKE ANY(array['%school%']) THEN 'school'
           WHEN business_name ILIKE ANY(array['%restaurant%']) THEN 'restaurant'
           WHEN business_name ILIKE ANY(array['%cafe%', '%café%', '%coffee%']) THEN 'cafe'
           ELSE 'other'
       END AS business_type
FROM sf_restaurant_health_violations
'''
