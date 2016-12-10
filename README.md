# learn-mongodb
Learn about mongodb

## INSTALL
- https://www.mongodb.com/
  - _TGZ_ | Program compact, can be use in **whatever location**


## FILES
- **MONGOD** **server**
- **MONGO** **client**

## RUN
- **Execute** the **server** in _/bin_
  - **Use** the _default_ _folder_ **/data/db**
```shell
mongod
```
  - **Use** _custom_ _folder_
```shell
mongod --db-path DIR
```
- *Execute** the **client** in _/bin_
```shell
mongo
```

## COLLECTIONS
- **CREATE**
```mongo
db.createCollection(name)
```
- **INSERT** | The _datas_ very _similar_ with format **json**, you can _insert_ whatever **object**
```mongo
db.collectionName.insert(data)
```
- **SEARCH ALL** | Equals _select_, **MULTIPLES** _RESULTS_
```mongo
db.collectionName.find()
```
- **SEARCH WHERE** | Equals _select_ with clause _where_, **MULTIPLES** _RESULTS_
=```mongo
db.collectionName.find(
  {"field": "value"}
  ) // AND
```
- **SEARCH ONE** | Equals _select_ with clause _where_, **ONE** _RESULT_
```mongo
db.collectionName.findOne(
  {"field": "value"}
  ) // AND
```

- **DELETE** _object_
```mongo
db.collectionName.remove(paramSearch)
db.collectionName.remove({_id: ObjectId("4892374893274283974392874298")})
```
- **UPDATE** _object_ | update _only_ **ONE** **OBJECT**
```mongo
db.collectionName.update(paramSearch, paramDataUpdate)
db.collectionName.update({_id: ObjectId("4892374893274283974392874298")})
```
- **UPDATE** _object_ | update **MULTIPLES** **OBJECT**
```mongo
db.collectionName.update(paramSearch, paramDataUpdate, {multi: true})
db.collectionName.update({_id: ObjectId("4892374893274283974392874298")}, {field: value}, {multi: true})
```




## OPERATORS
- **$or** | _Clause_ **where** with **or**
```mongo
db.collectionName.find(
{
  $or: [{"field": "value"}, {"field": "value2"}]
}) // OR
```
- **$in** | _Clause_ **where** with **in**
```mongo
db.collectionName.find(
{
  field:{
    $in: [value1,vlaue2,valie3]
  }
}) // IN
```
- **$set** | _UPDATE_ **FIELD**
```mongo
db.collectionName.update(paramSearch, {
  $set: {
    "field": "value"
  }
  })
```
- **$push** | _ADDED_ value in array, "push"
```mongo
db.collectionName.update(paramSearch, {
  $push: {
    "field": "value"
  }
  })
```
- **$each** | _LOOP_ value in array
```mongo
db.collectionName.update(paramSearch, {
  $push: {
    $each: {
      [{"field": "value"}, {"field": "value"}]
      }
  }
  })
```
- **$gt** || **Greater than** (maior que)
```mongo
db.collectionName.find({
  field: {
    $gt: value
  }
  })
```

## FUNCTIONS
- **FORMAT** the _results_ **pretty()**
```
db.collectionName.find().pretty()
```
- **ORDER** _fields_ **sort()**
  - type = 1 = **ASC**
  - type= -1 = **DESC**
```
db.collectionName.find().sort({field: type});
```
- **LIMIT** results_ **limit()**
```
db.collectionName.find().limit(number);
```


## OBSERVATIONS
- **COLLECTIONS** | Equals _tables_
- Default the **server** run _folder_ **/data/bd** | you can _CHANGE_
- _EDIT_ **bash_profile**
```vim
export PATH=$PATH:DIR_MONGOD
```
- [**OPTIONAL**] _use_ **quotation marks("")** in field names
```json
{
  "field": "value"
}
```
- Your **estructure** is **DINAMIC**
_ **VERY** _used_ in **Search for proximity**
- **DEFAULT** **FIND**
- **COLLECTION UPDATE** | **DANGER** this _function_ replace **ALL object**, for update especific _field_ use operator **$set**
