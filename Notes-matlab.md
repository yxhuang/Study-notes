Matlab study notes
==========================================
---------------------------------------

Matlab data type
--------------------------------------------
Matlab has 15 basic data types, every type is in the form of arrays or matrices.

**generate strin gs:** `str="Hello World"`  
**Inquire data type:** `class(x)`  
**Complex numbers:** `x=pi+4i`  
**Logic type:** `x=[ture false]`  

* **make comparison:** note that the two strings must be at the same length
	    
        string1 = 'I love you    '
        string2 = 'I love chengxu'
        x = string1 == string2
 		x =
        1     1     1     1     1     1     1     0     0     0     0     0     0     0

###Cells in matlab###
Cells is a sturcture similar to the list in R language I think. It can consist many different type of data element in one cell.

* **example**:

	    A={[1,2,3;4,5,6],['Chengxu']}
		A = 
    	[2x3 double]    'Chengxu'
	we can also use command `cellplot(A)` to visualize the cell's structure.  
	we can use `celldisp(A)` to display the actual content of the cell.

-------------------------------------------------------------------















Matrix
========================================================================
--------------------------------------

 In matlab, I think it is similar to R, all scalars, vectors and matrixes are all matrixes.

###Vector##
	x=(1:2:10)  中间的2是隔多少个。
    x =

     1     3     5     7     9

### Basic Matrix##
examples: A=[1,2,3;4,5,6]

     A =
     1     2     3
     4     5     6
    
     zeros(2,2)
     ans =
     0     0
     0     0

	ones(2,2)
	ans =
     1     1
     1     1
	
	randn(2,2)
	ans =
     -0.2050    1.4897
     -0.1241    1.4090

###Vist the elements of matrix###
1. **use doulbe subscripts:**   A(1,2)
2. **use single subscripts:**   A(4) = A(2,2) if A is a 2 by 2 matrix

###link the matrices###
1. **horizontal merge:** C = [A B] or C = [A, B] Or use function: C= cat(2,A,B)
2. **Vertical merge:** C = [A;B] or use function: C = cat(1,A,B)



###Obtain the size information of matrix###
1. **The longest dimension of the matrix:** `length(A)`
2. **The num. of elements of the matrix:**  `numel(A)`
3. **The dimensions of the matrix:** `ndims(A)`
4. **The size of the matrix:** `size(A)`


###Matrix Operations###
- **Matrix transpose:** B=B'
- **Matrix replicate:** N= repmat(unit,3,2)
   把unit举证作为子分块复制成3×2的新的大矩阵
- **diagonal merge:**  use funcion: C = blkdiag(A, B)
   example: 
         
		A=[1,2,;3,4]
        A =
    		 1     2
     		 3     4
		B=[5,6,7;8,9,0]
		B =
   		  5     6     7
          8     9     0
        C = blkdiag(A, B)
		C =
    	 1     2     0     0     0
     	 3     4     0     0     0
     	 0     0     5     6     7
     	 0     0     8     9     0

- **Enlarge or reduce the matrix:**
  1. **Enlarge:** supposed already exist a matrix A (2*2), just use A(:,3)=3 to add another column or A(3,3)=1 to add another value at that position, the other value will automatically be zero.
  2. **Reduce:** use sucha as 
    	
			A(:,3)=[ ]    
    	 	A(2, :) = []
   
       
- **Matrix addition, subtraction, multiplication and division:**
1. **Addition:** `A+B`  
2. **Substraction:**`A-B`  
3. **Multiplication:**`A*B`  
4. **Division:**`A/B` 

Notes: the addition and subtraction operation should always have the same dimension.   
`A/B=A*inv(B)`, `inv(B)` is the Inverse of the matrix B.

- **The power of matrix:**  
 example:
		
		A^3
		2.^A %this is using 2 as base and use each element in matrix A as its power              to get a new matrix.

- **Matrix operations by elements**  
This is the type of operation design by matlab to deal with elements in each matrix efficiently.  
 * 按位乘：`A.*B`
 * 按位右除：`A./B`
 * 按位左除：`A.\B`
 * 按位幂：`A.^B` 
<br /><br /><br />
				
   
* **Rational operations and Logical Operations:**
 - 大于(或等于)：`>  (>=)`
 - 小于(或等于)：`<  (<=)`
 - 等于：`==`
 - 不等于：`~=`
 - And: `&`
 - Or: `|`
 - Not: `~`





 







-----------------------------------------------------------







