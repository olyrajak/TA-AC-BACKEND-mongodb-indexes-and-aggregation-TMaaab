<!-- var pipeline = [

    { $unwind: "$tags" }

];

db.questions.aggregate(pipeline); -->

<!--  var pipeline = [
    {$group: {_id: null,count: { $sum: 1 } }}
]

 db.questions.aggregate(pipeline); -->

 <!-- 
    Total answers count overall and question specific as well

var pipeline = [
    {
      $group: {
          _id: "$questions",
            count: { $sum: { $unwind: "$ansewrs" }},
      },
  },
]

 db.questions.aggregate(pipeline); -->

 <!-- 
    Count total reputation of a user

> var pipeline = [
   {$group: {
        _id: null,
        count: {$sum: "$reputation"}
    }}
]

> db.users.aggregate(pipeline);

    total views on a particular day

> var pipeline = [
    {$project: { "date":{$year:"$registered"}}},
    {$match:   {date: ISODate('2022-08-30')}},
    {$group: {
      _id: $date,
      count: { $sum: "$views" },
      }},
]

> db.questions.aggregate(pipeline);

    Count total answer by a particular user

> var pipeline = [
   {$group: {
        _id: "$user",
        count: {$sum: "$answer"}
    }}
]

> db.questions.aggregate(pipeline); -->
