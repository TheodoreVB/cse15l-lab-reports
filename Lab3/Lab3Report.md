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

This JUnit test fails with the output "arrays first differed at element [2]; expected:<2> but was:<3>". Printing the array to console after reversing it shows that the array is actually being output as [4,3,3,4]. (The first dot in the JUnit output is `testReverseInPlace`, which passes, the `4334` is my debug output, and the E is `testReverseInPlace2`, which is the one that fails.) 
