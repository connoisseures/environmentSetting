mongoDB
---
+ https://docs.mongodb.com/manual/introduction/
+ https://www.mongodb.com/blog/post/getting-started-with-python-and-mongodb
+ https://realpython.com/introduction-to-mongodb-and-python/
+ aggregation
  - https://docs.mongodb.com/manual/aggregation/
  - https://docs.mongodb.com/manual/reference/operator/aggregation/match/
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
