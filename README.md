## Mid Unit-1 Review


## Strings

1. **Given a String, return a String with each letter uppercased**

Input: `Hello, there`

Output: `HELLO, THERE`

```swift
// Answer: 

var input = "Hello, there"

var inputUppercased = input.uppercased()
```

2. **Given a String, return a String alternating between uppercase and lowercase letters**


Input: `Hello, there`

Output: `HeLlO, tHeRe`
```swift
// Answer: 

var newString = ""
for (index, char) in input.enumerated() {
   
    if index % 2 == 0 {
        newString += char.uppercased()
    } else {
        newString += String(char)
    }
}

print(newString)
```

3. **Given a String, return a String with all occurrences of a given letter removed**

Input: `Hello, there`

Output: `Hllo, thr`

```swift
// Answer: 

var noEString = ""
for char in input {
    
    if char != "e" {
        noEString += String(char)
    }
}

print(noEString)
```
## Arrays


1. **Given an array of type [Int], return the largest element**

Input: `[1,5,2,4,1,4]`

Output: `5`

```swift
// Answer:

let inputArr = [1,5,2,4,1,4]

 let maxNum = inputArr.max()

print(maxNum)
```

2. **Given an array of type [Int], return the smallest element**

Input: `[1,5,2,4,1,4]`

Output: `1`
```swift
// Answer:

let minNum = inputArr.min()
```

3. **Given an array of type [Int], return its sum**

Input: `[1,5,2,4,1,4]`

Output: `17`

```swift
//Answer:

var sum = 0

for num in inputArr {
    sum += num
}
print(sum)
```
4. **Given an array of type [Double], return its average**

Input: `[3,4.5,7.5,2,1]`

Output: `3.6`

```swift
//Answer:

var sum = 0.0
var counter = 0.0
var avg: Double = 0

var doubleArray: [Double] = [3,4.5,7.5,2,1]

for num in doubleArray {
     sum += num
    counter += 1
}

avg = sum/counter
```
5. **Given an array of type [Double] and a Double, return the sum of all numbers in the array greater than a given number**

Input: `[3,4.5,7.5,2,1], 3`

Output: `12`

```swift
//Answer:

var newArr = doubleArray.filter({$0 > 3})
var sumOfDoubles = newArr.reduce(0, {$0 + $1}))
```

6. **Given an array of type [Double], return the product of all the elements**

Input: `[3,4.5,7.5,2,1]`

Output: `202.5`

```swift
//Answer:

var doubleArray: [Double] = [3,4.5,7.5,2,1]
var productOfDoubles = doubleArray.reduce(1, {$0 * $1})
```
7. **Given an array of type [Int], return the second smallest value in the array**

Input: `[3,6,1,9,4,8]`

Output: `3`

```swift
//Answer:

var intArr = [3,6,1,9,4,8]

var sortedIntArr = intArr.sorted()

var secondSmallestInt = sortedIntArr[1]

print(secondSmallestInt)
```

## Optionals

1. **Given an array of type [String?] return an array of [String] removing all nil values**

Input: `[nil, "We", "come", nil, "in", "peace"]`

Output: `["We", "come", "in", "peace"]`

```swift
//Answer:

var noNilArr = [String?]()
var noNilArr2 = [String]()

for word in strArray {
    
    if let nonNil = word {
        noNilArr2.append(nonNil)
    }
}

print(noNilArr2)
```
2. **Given an array of type [String?]? return an array of [String] removing all nil values**

Input: `nil`

Output: `[]`

3. **Given an array of type [Int?] return the sum of all non-nil values.  Use guard statements in your solution.**

Input: `[4, nil, 9, 5, nil]`

Output: `18`

```swift
//Answer:

var nilArr = [4, nil, 9, 5, nil]

func noNil(arr: [Int?]) -> Int {
var nonNilSum = 0

for num in arr {
    guard let nonNil = num
    else { continue } // continue is used so that it doesnt just return anyting once a nil is found. 
    nonNilSum += nonNil
}
   return nonNilSum
}

noNil(arr: nilArr)
```

4. **Given an array of type [Int?]? return the sum of all non-nil values.  Use guard statements in your solution.**

Input: `nil`

Output: `0`

```swift 
//Answer:

var optIntArr: [Int?]?
optIntArr = [nil]

var newIntArray = [Int]()

if let unwrappedIntArr = optIntArr {
    for num in unwrappedIntArr{
        if let number = num {
        newIntArray.append(number)
        }
    }
}
print(newIntArray)
```


5. **Given an array of type [Int?] and an optional Int, return the sum of all values not equal to the given number.  If the given number is nil, return the sum of all non-nil values.**

Input: `[1, 1, nil, 3, 5, nil, 1, nil, 3, 5, nil, 5, nil, 3], 1`

Output: `24`

```swift 
//Answer:

for num in inputOfInt {
    if let unwrappedNum = num {
        if unwrappedNum != filterNum {
            newIntArray.append(unwrappedNum)
        }
    }
}
var sum1 = newIntArray.reduce(0, +)
print(sum1)
```

## Dictionaries

1. **Given an array of type [String], return a copy of the array with all duplicate values removed**

Input: `["apple", "apple", "banana", "banana", "banana", "cake", "cake"]`

Output: `["apple", "banana", "cake"]`

```swift
//Answer:

var inputArray = ["apple", "apple", "banana", "banana", "banana", "cake", "cake"]

var inputAsSet = Set(inputArray) // removes duplicates

var uniqueArr = [String]()

for element in inputArray {
    if !uniqueArr.contains(element) {
         uniqueArr.append(element)
    }
}

print(uniqueArr)
```

2. **Given a String, find the most frequently occurring letter**

Input: `Never trust a computer you can't throw out a window ~ Steve Wozniak`

Output: `t
```swift
// Answer:

input = "Never trust a computer you can't throw out a window ~ Steve Wozniak"

var frequencyDict = [Character: Int]()

for char in input.lowercased() {
    if char != " " {
        if let value = frequencyDict[char]{
            frequencyDict[char] = value + 1
        } else {
            frequencyDict[char] = 1
        }
    }
}
print(frequencyDict)


var highestOccurance = 0
var highestOccuringChar = ""

for (key, value) in frequencyDict {
    if value > highestOccurance {
        highestOccurance = value
        highestOccuringChar = key.description
        
    }
    
}

print(highestOccuringChar)
```

3. **Given an array of type [Int], return a copy of the array that contains only elements that appear at least twice**

Input: `[1,1,2,3,3,3,4,5,6,6,7]`

Output: `[1,3,6]`

```swift
// Answer:
var duplicatesArr = [Int]()
//Output: [1,3,6]

for num in numArr {
    var counter = 0
    for num1 in numArr {
        if num == num1 && !duplicatesArr.contains(num){
            counter += 1
            if counter > 1 {
                       duplicatesArr.append(num)
                   }
        }
       
    }
}

print(duplicatesArr)
```

4. **Given a String, find the second most frequently occurring letter in a string**

Input: `Never trust a computer you can't throw out a window ~ Steve Wozniak`

Output `o`

```swift
// Answer:
var frequencyDict = [Character: Int]()

for char in input.lowercased() {
    if char != " " {
        if let value = frequencyDict[char]{
            frequencyDict[char] = value + 1
        } else {
            frequencyDict[char] = 1
        }
    }
}
print(frequencyDict)

// finds the highest occurance

var highestOccurance = frequencyDict.values.max() ?? 0
var secondhighest = 1
var secondhighestChar: Character = " "
var highestOccuringChar: Character = " "

for (key, value) in frequencyDict {
    if value < highestOccurance && value > secondhighest {
        secondhighest = value
        secondhighestChar = key
        
    }
    
}

print(secondhighestChar)
```

## Closures

1. **Given an array of type [String], return an array that contains the Strings sorted alphabetically with capital letters first (Swift will do that part automatically)**

Input: `["Never", "trust", "a", "computer", "you", "can't", "throw", "out", "a", "window"]`

Output: `["Never", "a", "a", "can\'t", "computer", "out", "throw", "trust", "window", "you"]`

```swift 
//Answer: 

var strArray2 = ["Never", "trust", "a", "computer", "you", "can't", "throw", "out", "a", "window"]

var newStrArray2 = strArray2.sorted()

print(newStrArray2)
```

2. **Given an array of type [String], return an array that contains the Strings sorted by length**

Input: `["Never", "trust", "a", "computer", "you", "can't", "throw", "out", "a", "window"]`

Output: `["a", "a", "you", "out", "Never", "trust", "can\'t", "throw", "window", "computer"]`

```swift 
//Answer: 

var sortedByLength = strArray2.sorted {$0.count < $1.count}

print(sortedByLength)
```

3. **Given an array of type [String], return an array containing all Strings at least 4 characters long**

Input: `["Never", "trust", "a", "computer", "you", "can't", "throw", "out", "a", "window"]`

Output: `["Never", "trust", "computer", "can\'t", "throw", "window"]`

```swift 
// Answer:

var arLeeat4Char = strArray2.filter{$0.count >= 4}
print(arLeeat4Char)
```

4. **Given an array of type [String], return a String containing all of the Strings from the array combined and separated by spaces.  Do this first without using the `joined(separator:) method`**

Input: `["Never", "trust", "a", "computer", "you", "can't", "throw", "out", "a", "window"]`

Output: `Never trust a computer you can't throw out a window`

```swift 
// Answer:

var combinedArray = ""

for word in strArray2 {
    combinedArray += (word + " ")
}

print(combinedArray)
```

## Enums


1. **Given an array of type [Int] and an instance of NumberType (defined below), return an array containing only all the even or odd numbers.**

```swift
enum NumberType {
    case even
    case odd
}
```

Input: `[1,2,3,4,5,6], NumberType.odd`

Output: `[1,3,5]`

2. **Given a String and an instance of StringType (defined below), return the String either lowercased or uppercased**

```swift
enum StringType {
    case lowercase
    case uppercase
}
```

Input: `"Design is not just what it looks like and feels like. Design is how it works", .uppercase`

Output: ``"DESIGN IS NOT JUST WHAT IT LOOKS LIKE AND FEELS LIKE. DESIGN IS HOW IT WORKS"``

3. **Given an array of type [FileStatus] (defined below) and an Int, return an array containing only files that were saved more than that many times**

```swift
enum FileStatus: CustomStringConvertible {
    case unsaved
    case saved(numberOfVersions: Int)
    var description: String {
        switch self {
        case .unsaved: return "Unsaved File"
        case let .saved(numberOfVersions): return "File that has been saved \(numberOfVersions) times"
        }
    }
}
```

Input: `[FileStatus.saved(numberOfVersions: 5), FileStatus.saved(numberOfVersions: 3), FileStatus.saved(numberOfVersions: 8)], 4`

Output: `[File that has been saved 5 times, File that has been saved 8 times]`
