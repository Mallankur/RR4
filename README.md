# RR4
Complex Operation on Mongodb 
# MongoDB Aggregation Pipeline Example

This repository contains an example of using MongoDB aggregation pipeline in a C# project. The provided aggregation pipeline is designed to perform specific operations on a MongoDB collection named "ankur".

## Prerequisites

Before using this example, make sure you have the following installed:

- .NET SDK
- MongoDB Server

## Usage



db.ankur.aggregate([
  {
    $unwind: "$DATA" // Deconstruct the DATA array
  },
  {
    $match: { // Filter documents to include only those with Dos values 5, 6, or 3
      "DATA.Dos": { $in: [1, 6, 3] }
    }
  },
  {
    $project: { // Project Dos and Value fields from the DATA array
      _id: 0,
      Dos: "$DATA.Dos",
      Value: "$DATA.Value"
    }
  }
])

