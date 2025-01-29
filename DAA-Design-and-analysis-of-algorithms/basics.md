## Basics of Algorithms

#### **Algorithm :** 
Specification of a sequence of valid steps which after a finite time convert valid **Input** to valid **Output**

<img src="../media/{3BFB04CC-14F4-4EB8-AC02-E8E9E5ADE586}.png" alt="Algorithm" width="600" height="200">

---

We try to solve various **problems** using Algorithms ,Let's look at an example 

### **The problem:** Given a Triangle △ and a point P in 2D, output "YES" if P ∈ △ otherwise "NO" 

**Input** <br>
Four points:  
- Three vertices of the triangle: **(x₁, y₁), (x₂, y₂), (x₃, y₃)**  
- One point P: **(x, y)**   
- `(x₁, y₁, x₂, y₂, x₃, y₃, x, y) ∈ Real Numbers` (float or integer).  

**Output**  
Print `"YES"` if `P ∈ △`, otherwise print `"NO"`.


<img src="../media/{5EDF6C01-1BC9-4F10-A367-3D5580B3E725}.png" alt="Input-output" width="800" height="600">

### **Solution:** 
Let's think how we can solve the problem:

- **Step 1 :** Find if the given Coordinates form a Triangle or Not, How ??

<img src="../media/{73548E4F-6DEF-4CE9-A070-267683CDEEDE}.png" alt="Input-output" width="400" height="200">

How do we determine if three points lie in a straight line ? :
- We can find the Area of the triangle if its 0 , they form a Straight line
<img src="../media/{AEAE9987-008C-4DF6-86DC-A9BF9BAE8690}.png" alt="Input-output" width="400" height="60">

- **Step 2 :** Find if the Point lies inside the triangle or not, How ?? <br>
    - The Point P makes three Triangles with the three vertices of the Triangle , If the Sum of these three triangles if more than the area of triangle The point lies outside the triangle otherwise it lies inside
    - If `Area( △ABP + △ACP + △BCP > △ABC)` PRINT `NO` else PRINT `YES`

<img src="../media/{C0A6B412-8CBE-4EAD-BF53-D320C8098338}.png" alt="Input-output" width="800" height="500">

- **Flowchart :** 

<img src="../media/{8CA10218-03E9-4E75-9654-06DAA85DF37D}.png" alt="Input-output" width="800" height="600">

- **CODE :**

```cpp

double areaOfTriangle(double, double, double, double, double, double);

void pointLiesInsideTriangle(double x1, double y1, double x2 , double y2, double x3, double y3 , double x , double y){
    double areaOfABC = areaOfTriangle(x1,y1,x2,y2,x3,y3);

    if(areaOfABC == 0) cout << "NO"; return; // NOT A TRIANGLE

    double area1 = areaOfTriangle(x1, y1, x, y, x3, y3);
    double area2 = areaOfTriangle(x1, y1, x2, y2, x, y);
    double area3 = areaOfTriangle(x, y, x2, y2, x3, y3);

    if ((area1 + area2 + area3) == areaOfABC){
        cout << "YES";
    }else{
        cout << "NO";
    }
}

double areaOfTriangle(double x1, double y1, double x2 , double y2, double x3, double y3){
    return 0.5 * abs(x1 * (y2 - y3) + x2 * (y3 - y1) + x3 * (y1 - y2));
}
```


> **📝 Note:**  
> There may be other Steps[Algorithm] to solve this problem  
> An problem can be solved using various algorithms , We will look how can we determine which algorithm is good or which is bad
