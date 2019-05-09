# sparked-spec

a design document for SparkEd V3

### Title 



### Introduction

SparkEd is a software for organizing and presenting educational and training contents for delivery on most platforms.  

The current implementation of SparkEd is documented [here](https://sparkeduab.github.io/sparked-manual/) and the source code lives [here](https://github.com/SparkEdUAB/SparkEd).

### Goals

As explained in the introduction SparkEd aims to solve the prooblem of content delivery and presentational of educational contents on most platforms and in remote areas.



### Implementation
 
SparkEd aims to be a platform that accomodates different institutions, this means that it doesn't matter whether you want to use in a school setup or in any organization that has and offers educational contents.
We currently have the following structures:

This is designed for organizations whose contents are divided in higher level hierachy.  

**eg:** university has schools then under a specific school there are different programs, then under a program there are courses which has units and topics which have resources.

![higher-level](https://sparkeduab.github.io/sparked-manual/docs/assets/school10.png)

This is a common implementation in most schools and organizations.   

![course-mid-lvel](https://sparkeduab.github.io/sparked-manual/docs/assets/school11.png)

An ideal implementation for High-School(Secondary)   
![subjects-low-level](https://sparkeduab.github.io/sparked-manual/docs/assets/school12.png)  


### Terminologies


### Data Model 

SparkEd uses MongoDB for Data storage and the following are the structure of different collections.

**Collections**

school 
```js
 {
   _id: String,
  name: String,
  code: String,
  createdAt: Date,
  createdBy: String,
 }

```
program
```js
 {
  _id: String
  name: String,
  code: String,
  schoolId: String,
  duration: String,
  createdAt: Date,
  createdBy: String,
 }

```
course
```js
 {
   _id: String
  name: String,
  code: String,
  details: {
     schoolId: String,
     programId: String,
     language: String,
  },
  createdAt: Date,
  createdBy: String,
 }
```

units

```js
{
  name: String,
  topics: Number,
  unitDesc: String,
    details: {
     courseId: String,
     programId: String,
     language: String,
  },
  createdAt: Date,
  createdBy: String,
}

```

topics

```js
{
  unitId: String,
  name: String,
  unit: String,
  resources: Array,
  'resources.$': Object,
  createdAt: Date,
  createdBy: String,
}
```
resources
Resources are basicall file objects that contain information about the files, these are the supported file types
- Videos(`mp4, webm`)
- Pdf(`pdf`)
- Image(`png, jpg, jpeg,`)
- Audio(`mp3, ogg`)
- Text(`txt`)


### Non-Goals

SparkEd is not meant to be a replacement for **Moodle** and this will remain the case, If you want to have a full fledged school management system, you might want consider Moodle or other options. 
The following are problems SparkEd doesn't solve  
- Discussion or Forum between Instructors and Learners
- Institution or Organization management system


### Milestones 
These will correspond with the indicated [milestones here](https://github.com/SparkEdUAB/sparked3.0-spec/milestones) when done


### Existing Solution

The current solution is implemented and named as SparkEd


### Proposed Solution 
> We will include new User Interface proposals soon here






### Scoping and Timeline

The project scoping will be included here soon as soon issues are broken down into their specifics


### Impact 


### Risks
