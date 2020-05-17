# Unit Testing Documentation template

Authors:

Date:

Version:



# Contents

- [Unit Testing Documentation template](#unit-testing-documentation-template)
- [Contents](#contents)
- [Black Box Unit Tests:](#black-box-unit-tests)
  - [Ex #1. order integers](#ex-1-order-integers)
  - [Ex #2. calories](#ex-2-calories)
  - [Ex #3. parallelogram](#ex-3-parallelogram)
  - [Ex #4. inventory](#ex-4-inventory)
- [White Box Unit Tests](#white-box-unit-tests)
    - [Test cases definition](#test-cases-definition)
    - [Code coverage report](#code-coverage-report)
    - [Loop coverage analysis](#loop-coverage-analysis)


- [White Box Unit Tests](#white-box-unit-tests)

  

# Black Box Unit Tests: 
 

## Ex #1. order integers
 

**Criteria for method orderIntegers(int v[]):**
	

- Inputs Type validity 

- Input vector length



**Predicates for method orderIntegers(int v[]):**

| Criteria                  | Predicate    |
| ------------------------- | ------------ |
| Type of parameter passed to orderIntegers         | Vectorof integers    |
|                                     | Vector of other types         |
|                                     | Not a vector        |
| Length of the input vector          | =3         |
|                                     | >3 or =0          |




**Boundaries for method orderIntegers(int v[]):**

| Criteria            | Boundary values             |
| ------------------- | --------------------------- |
| Length of the input vector     | 0, 1, 2, 3, 4, maxsize-1, maxsize|






 **Combination of predicates for method orderIntegers(int v[])**

| Input vector | Lenght of input vector |  Valid/Invalid | Description of the test case|JUnit test case     |
| ------------- | -------- | ------------------- | --------------------------------------------- | ------------------------ | 
| Intger vector          | >3        | I     |  int v[]=[1,2,3,4];<br /> orderIntegers(v)--> Exception     | com.polito.exercise1.blackboxtests.tc1     | 
| Intger vector          | 0        | I     |  int v[]=[];<br /> orderIntegers(v)--> Exception     | com.polito.exercise1.blackboxtests.tc1     |
| Intger vector          | =3        | V     |  int v[]=[1,2,3];<br /> orderIntegers(v)--> [3,2,1] , 3     | com.polito.exercise1.blackboxtests.tc1     |
|Other types vector         | -        | I    |  char v[]=['a','d','i'];<br /> orderIntegers(v) --> Exception     | com.polito.exercise1.blackboxtests.tc2     |
|Not a vector            | -        | I  |  int v=2;<br /> orderIntegers(v) --> Exception     | com.polito.exercise1.blackboxtests.tc3     |  



## Ex #2. calories

**Criteria for method acceptableToEat( int carb, int protein, int fat):**
	

- Number of parameters
- Type of parameters
- Sign of parameters
- Total amount of calories
- Constraint (carb + protein ) / fat



**Predicates for method acceptableToEat( int carb, int protein, int fat):**

| Criteria                  | Predicate    |
| ------------------------- | ------------ |
| Type of parameters passed to acceptableToEat | 3 integers    |
|                                             | at least one non integer |
| Number of parameters                | =3         |
|                                     | <3 or =0          |
| Sign of parameters                  | Positive         |
|                                     | Negative          |
| Total Calories                      | < 1000         |
|                                     | >= 1000          |
| Constraint (carb + protein ) / fat  | >0.5          |
|                                     | <=0.5           |




**Boundaries for method acceptableToEat( int carb, int protein, int fat):**

| Criteria            | Boundary values             |
| ------------------- | --------------------------- |
| Type of parameters passed to acceptableToEat | -|
| Number of parameters                | 3, 2 , 4 , 0 |
| Sign of parameters                  | 0, -1, 1         |
| Total Calories                      | 0, 1, 999, 1001,1000,1001, maxint-1, maxint  |
| Constraint (carb + protein ) / fat  |0, mindouble, 0.49 0.50, 0.51,mindouble,maxdouble-mindouble, maxdouble|


 **Combination of predicates for method acceptableToEat( int carb, int protein, int fat):**

| Type of parameters for acceptableToEat |Number of parameters| Signs of input parameters|Total amount of calories | Constraint (carb + protein ) / fat | Valid/Invalid | Description of the test case | JUnit test case |
| ---------------- | ---------------- | ------------------------- | ------------------- | ------------- | ------------------------------------------------------------ |----|----|
| Integer         |=3 |  All positive| <1000         |  >0.5         | V          | acceptableToEat(7,7,7) --> true                                     | com.polito.exercise2.blackboxtests.tc1 |
|      | ||       |  <=0.5         | V            | acceptableToEat(15,1,100) --> false | com.polito.exercise2.blackboxtests.tc2 |
|      |||>=1000        |  -       | V            | acceptableToEat(200,100,300) --> false | com.polito.exercise2.blackboxtests.tc3 |
|      ||at least one negative|-        |  -       | I            | acceptableToEat(-10,10,10) --> Exception | com.polito.exercise2.blackboxtests.tc4 |
|   |>3|-| -         |  -        | I | acceptableToEat(50,30,70,90) --> Exception|com.polito.exercise2.blackboxtests.tc6 |
|   |<3|-| -         |  -        | I | acceptableToEat() --> Exception|com.polito.exercise2.blackboxtests.tc5 |
| All other types        |-|-| -         |  -        | I | acceptableToEat(99.2,14.4,46.3) --> Exception|com.polito.exercise2.blackboxtests.tc7 |





## Ex #3. parallelogram


**Criteria for method parallelogram(int x1, int x2, int x3, int x4, int y1, int y2, int y3, int y4)**
- Number of parameters
- Type of parameters
- Sign of parameters
- Slope of the bases
- Slope of the sides
- Lengh of the bases
- Lengh of the sides

**Predicates for method parallelogram(int x1, int x2, int x3, int x4, int y1, int y2, int y3, int y4)**

| Criteria                  | Predicate    |
| ------------------------- | ------------ |
| Number of parameter       | 8            |
|                           | <=7 and >=9  |
| Type of parameters        | All integer |
|                           | At least one non integer |
| Sign of parameters        | All positive >=0 |
|                           | All negative <0 |
|                           | Mixed sign       |
| Slope of the bases | (y2-y1)/ (x2-x1) =   (y4-y3)/(x4-x3)  |
|                    | (y2-y1)/ (x2-x1) !=   (y4-y3)/(x4-x3) |
| Slope of the sides | (y4-y2)/ (x4-x2) =   (y3-y1)/(x3-x1)|
|                    | (y4-y2)/ (x4-x2) !=   (y3-y1)/(x3-x1) |
| Lengh of the bases | sqrt[ (x2-x1)^2 + (y2-y1)^2 ] = sqrt[ (x4-x3)^2 + (y4-y3)^2 ]  != 0|
|                    | sqrt[ (x2-x1)^2 + (y2-y1)^2 ] != sqrt[ (x4-x3)^2 + (y4-y3)^2 ] |
|                    | sqrt[ (x2-x1)^2 + (y2-y1)^2 ] = 0 or sqrt[ (x4-x3)^2 + (y4-y3)^2 ] = 0 |
| Lengh of the sides | sqrt[ (x3-x1)^2 + (y3-y1)^2 ] = sqrt[ (x4-x2)^2 + (y4-y2)^2 ] != 0 |
|                    | sqrt[ (x3-x1)^2 + (y3-y1)^2 ] != sqrt[ (x4-x2)^2 + (y4-y2)^2 ] |
|                    | sqrt[ (x3-x1)^2 + (y3-y1)^2 ] = 0 or sqrt[ (x4-x2)^2 + (y4-y2)^2 ] = 0 |

**Boundaries for method parallelogram(int x1, int x2, int x3, int x4, int y1, int y2, int y3, int y4)**:

| Criteria            | Boundary values             |
| ------------------- | --------------------------- |
| Sign of coordinates | -mindouble, 0, mindouble  |
| Slope of the bases  | -maxdouble,-mindouble,0, mindouble,maxdouble |
| Slope of the bases  | -maxdouble,-mindouble,0, mindouble,maxdouble |
| Lengh of the bases  | 0, mindouble |
| Lengh of the sides  | 0, mindouble |


 **Combination of predicates for method parallelogram(int x1, int x2, int x3, int x4, int y1, int y2, int y3, int y4)**

|Type of parameters| Number of parameter | Sign of coordinates | Lengh of the bases | Lengh of the sides | Valid/Invalid | Description of the test case |
|--| -- | -- | -- | ---------- | ------------------- | -- | -- |
|All integer| 8    | All positive >=0 | sqrt[ (x2-x1)^2 + (y2-y1)^2 ] = sqrt[ (x4-x3)^2 + (y4-y3)^2 ] != 0 | sqrt[ (x3-x1)^2 + (y3-y1)^2 ] = sqrt[ (x4-x2)^2 + (y4-y2)^2 ] != 0 | V    | T1(parallelogram(1, 3, 2, 4, 0, 0, 1, 1)) -> 2 |
|All integer| 8    | All positive >=0 | sqrt[ (x2-x1)^2 + (y2-y1)^2 ] = sqrt[ (x4-x3)^2 + (y4-y3)^2 ] != 0 | sqrt[ (x3-x1)^2 + (y3-y1)^2 ] != sqrt[ (x4-x2)^2 + (y4-y2)^2 ] | V    | T2(parallelogram(1, 3, 2, 4, 0, 0, 1, 0.5)) -> -1 |
|All integer| 8    | All positive >=0 | sqrt[ (x2-x1)^2 + (y2-y1)^2 ] = sqrt[ (x4-x3)^2 + (y4-y3)^2 ] != 0 | sqrt[ (x3-x1)^2 + (y3-y1)^2 ] = 0 or sqrt[ (x4-x2)^2 + (y4-y2)^2 ] = 0 | V    | T3(parallelogram(1, 3, 2, 4, 0, 0, 1, 0)) -> -1 |
|All integer| 8    | All positive >=0 | sqrt[ (x2-x1)^2 + (y2-y1)^2 ] != sqrt[ (x4-x3)^2 + (y4-y3)^2 ] | - | V    | T4(parallelogram(1, 3, 2, 5, 0, 0, 1, 1)) -> -1 |
|All integer| 8    | All positive >=0 | sqrt[ (x2-x1)^2 + (y2-y1)^2 ] = 0 or sqrt[ (x4-x3)^2 + (y4-y3)^2 ] = 0 | - | V    | T5(parallelogram(1, 1, 2, 4, 0, 0, 1, 1)) -> -1 |
|All integer| 8    | All negative <0 | - | - | V    | T6(parallelogram(-1, -1, -2, -4, -1, -3, -2, -1)) -> -1 |
|All integer| 8    | Mixed | - | - | V    | T7(parallelogram(1, -1, 2, 4, 1, 3, 2, 1)) -> -1 |
|All integer| 7    | - | - | - | I    | T7(parallelogram(1, 1, 2, 4, 1, 3, 2)) -> Exception |
|All integer| 9    | - | - | - | I    | T8(parallelogram(1, 1, 2, 4, 1, 3, 2, 5, 9)) -> Exception |
|At least one non integer| -    | - | - | - | I    | T9(parallelogram(1, 1, 2, 4, 1, 3, 2, 5.5)) -> Exception |








## Ex #4. inventory


**Criteria for class inventory”**

- Unique itemCode
- Valid availability number


**Predicates for class inventory”**

| Criteria                  | Predicate    |
| ------------------------- | ------------ |
| Unique itemCode           | unique and not NULL |
|                           | non unique or NULL  |
| Valid availability number       | > 0 |
|                                 | 0  |
|                                 | < 0  |


**Boundaries for class inventory”**:

| Criteria            | Boundary values             |
| ------------------- | --------------------------- |
| Availability number | -1, 0, 1  |


 **Combination of predicates for class inventory”**

| Unique itemCode  | Availability number | Valid/Invalid | Description of the test case |
| -- | -- | -- | -- | -- |
| unique and not NULL | >0 | V    | T1(addItem(i)) -> OK |
| unique and not NULL | 0  | V    | T2(subtractItem(i)) -> ItemNotAvailable |
| unique and not NULL | <0  | I    | T2(subtractItem(i)) -> Exception |
| non unique or NULL  | >=0 | I    | T3(availabilityItem(i)) -> WrongItemIDException |
| non unique or NULL  | 0  | I    | T3(availabilityItem(i)) -> WrongItemIDException |
| non unique or NULL  | <0 | I    | T3(availabilityItem(i)) -> WrongItemIDException |




# White Box Unit Tests

### Test cases definition

```
<Report here all the created JUnit test cases, and the units/classes they test >
```

| Unit name | JUnit test case                              |
| --------- | -------------------------------------------- |
| Converter | com.polito.converter.<br />whiteboxtests.tc1 |
| Converter | com.polito.converter.<br />blackboxtests.tc2 |
|           |                                              |

### Code coverage report

```
<Add here the screenshot report of the code and branch coverage obtained using
the Jacoco tool. >
```

### Loop coverage analysis

```
<Identify significant loops in the units and reports the test cases
developed to cover zero, one or multiple iterations >
```

| Unit name | Loop rows | Number of iterations | JUnit test case                              |
| --------- | --------- | -------------------- | -------------------------------------------- |
| Converter | 7-11      | 0                    | com.polito.converter.<br />whiteboxtests.tc1 |
|           |           | 1                    | com.polito.converter.<br />whiteboxtests.tc2 |
|           |           | 2+                   | com.polito.converter.<br />whiteboxtests.tc4 |
| ...       | ...       | ...                  | ...                                          |

