PostgreSQL
---
+ https://www.postgresql.org/about/

mongoDB
---
+ https://docs.mongodb.com/manual/introduction/
+ https://www.mongodb.com/blog/post/getting-started-with-python-and-mongodb
+ https://realpython.com/introduction-to-mongodb-and-python/
+ http://zetcode.com/python/pymongo/
+ https://docs.mongodb.com/ecosystem/drivers/pymongo/
+ match
  - https://docs.mongodb.com/manual/reference/operator/aggregation/match/
+ aggregation
  - https://docs.mongodb.com/manual/reference/operator/aggregation-pipeline/
  - https://docs.mongodb.com/manual/aggregation/
  - https://www.techyhunger.com/mongodb-unwind-operator-aggregation-stage
  - https://docs.mongodb.com/manual/reference/operator/aggregation/match/
  - https://techbrij.com/mongodb-query-select-filter-child-nested-array
+ find
  - https://docs.mongodb.com/manual/reference/method/db.collection.find/
  - db.collection.find(query, projection)
  ```python
      for doc in annotation_collection.find({}, {'_id':1}):
        print(doc)
      ## print all doc and only '_id' file is returned
      
      for doc in annotation_collection.find({'_id':1}):
        print(doc)
      ## print doc which '_id' filed is equal to 1
  ```
+ is existed and remove
  - https://stackoverflow.com/questions/9822575/how-to-check-in-pymongo-if-collection-exists-and-if-exists-empty-remove-all-fro
