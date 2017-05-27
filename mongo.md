 0. query:
 mongoimport --db learn --collection unicorns --drop --file c:/data/dataSample.json --jsonArray
 	result:
	 	2017-05-26T23:45:24.186+0300    connected to: localhost
		2017-05-26T23:45:24.188+0300    dropping: learn.unicorns
		2017-05-26T23:45:24.454+0300    imported 201 documents

1. query:
	db.unicorns.find({"scores":{$elemMatch:{"score":{$gt:87,$lt:93}}}}).pretty()

2. query:
 	db.unicorns.aggregate([{$unwind:"$scores"},{$match:{"scores.score":{$gt:90},"scores.type":"exam"}}]).pretty()

3. query:
	db.unicorns.update({"name":"Dusti Lemmond"},{$set:{"accepted":true}},{multi:true})