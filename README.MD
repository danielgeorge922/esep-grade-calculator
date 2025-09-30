# ESEP Grade Calculator

This library is a simple utility to calculate your grades.

Runtime requirements:
Golang 1.24+

# Each file in the repo:
1. README.md - This is just the file that goes over useful information about the repo as a whole. It goes over things like tech requirements, purpose, and commands that would be useful when working in the repo.
2. go.mod - This is declaring the path for the go module that we are defining as well as the version of Go that is being used in the project.
3. grade_calculator.go - This is the core library that contains the logic (not the utilization) of the actual grade calculator. This defines both types for objects and data structures being used as well as functions that use those types.
4. grade_calculator_test.go - These are unit tests that go over different implementations / testings of the library functions to make sure they are working as intended. This goes over things like if someone gets an 100 on all 3 groups do they get an A.


Here is a basic version of how the code can be utilized

`
package main

import (
	"fmt"
	"esep/grade-calculator"
)

func main() {
	// 1. Create a new calculator instance
	calculator := esepunittests.NewGradeCalculator()
    
	// 2. Add grades for different categories
	calculator.AddGrade("Homework 1", 95, esepunittests.Assignment)
	calculator.AddGrade("Midterm Exam", 82, esepunittests.Exam)
	calculator.AddGrade("Final Exam", 88, esepunittests.Exam)
	calculator.AddGrade("Ethics Paper", 91, esepunittests.Essay)

	// 3. Get the final letter grade
	finalGrade := calculator.GetFinalGrade()

	fmt.Printf("The student's final grade is: %s\n", finalGrade)
}
`

Run unit tests:
```
cd grade-calculator/
go test ./...
```

Run unit tests with code coverage:
```
cd grade_calculator/
go test -coverprofile=coverage.txt ./...
```