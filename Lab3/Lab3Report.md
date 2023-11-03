# Lab Report 3

## Bugs

### The buggy code before being fixed:
```cpp
  static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }
```
### The failure-inducing input for the JUnit test:
```cpp
	@Test 
	public void testReverseInPlace2() {
    int[] input1 = { 1, 2, 3, 4 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 4, 3, 2, 1 }, input1);
	}
```
### The non-failure-inducing input for the JUnit test:
```cpp
	@Test 
	public void testReverseInPlace() {
    int[] input1 = { 3 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 3 }, input1);
	}
```
### Image of JUnit output:
![Image](JUnitFail.png)

This JUnit test fails with the output "arrays first differed at element [2]; expected:<2> but was:<3>". Printing the array to console after reversing it shows that the array is actually being output as [4,3,3,4]. (The first dot in the JUnit output is `testReverseInPlace`, which passes, the `4334` is my debug output, and the E is `testReverseInPlace2`, which is the one that fails.) This bug is due to a few issues with the code, the first being that `arr[i] = arr[arr.length - i - 1];` overwriting the first half of the array with the second half, but doesn't write the first half to the second half. This is solved by using a temporary variable, `int temp = 0`, to hold the elements from the front to store in the back after having been overwritten (the first and last lines of the for loop). However, a new bug will arise from this fix, because the array is iterating over the whole array, so it will basically 'un-reverse' itself when it iterates through the second half. The fix for this is to have the for loop stop halfway through the array using `i < arr.length / 2`.

### The fixed code:
```cpp
  static void reverseInPlace(int[] arr) {
    int temp = 0;
    for(int i = 0; i < arr.length / 2; i += 1) {
      temp = arr[i];
      arr[i] = arr[arr.length - i - 1];
      arr[arr.length - i - 1] = temp;
    }
  }
```


## Researching Commands




