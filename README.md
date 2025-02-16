# MongoDB Aggregation Pipeline Bug: Incorrect $inc Operator Placement

This repository demonstrates a common error when using the `$inc` operator within a MongoDB aggregation pipeline.  The `$inc` operator is incorrectly placed, leading to unexpected results in the aggregation output.

## Bug Description
The primary issue lies in the placement of the `$inc` operator in the pipeline.  It should be applied *before* the `$project` stage if you want to increment the count value for each document. 

## Solution
The solution involves moving the `$inc` stage earlier in the pipeline, before the `$project` stage that selects the desired fields.