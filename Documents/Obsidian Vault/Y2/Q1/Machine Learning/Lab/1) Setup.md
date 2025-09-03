## Anaconda
To use anaconda commands, go to "search" in bottom bar (aka start menu) and search for anaconda prompts. Here, you'll be able to enter your prompts

First go to correct repository of the lab assignment, then run:
```jupyter notebook``` 
- Lab week 1: ```cd "C:\Users\lewan\Downloads\Lab 1 - Introduction"```
## Python
Running code can be done with ```shift+enter```
```arr[start:end]``` select elements between start (inclusive) and end (exclusive) 
## NumPy
Better than regular python lists 
- More space efficient 
	- Python list store pointers, whereas numpy arrays are actually stored as one block of data
- ```.shape``` determines number of rows (index 0) and number of columns (index 1)
- ```np.where(<boolean on an np.array>)``` to filter entries of an array
- ```np.arange(<range>)``` to create an array with integers from start (inclusive) until end (exclusive) of range
- ```np.mean()``` to select mean of array
- **Selecting particular indices:** ```arr[<indices_arr>]``` which can be combined with ```temp = np.arange(<range>)
	indices_arr = np.where(temp[:] % 2 ==0)```
- **Broadcastable arrays:** you can directly manipulate arrays (arr_1 * arr_2 etc.) iff (they are of the same shape or one's dimension is 1)
- ```np.argmax(<arr>)``` selects the index of the maximum element in given array
- **Linear algebra:** we can do matrix on arrays multiplication using "@" 