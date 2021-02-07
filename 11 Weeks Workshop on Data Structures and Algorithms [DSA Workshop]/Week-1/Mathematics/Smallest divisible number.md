# [Smallest divisible number ](https://practice.geeksforgeeks.org/problems/smallest-divisible-number/1/?track=dsa-workshop-1-mathematics&batchId=308)
<p>Given a number N, find an integer denoting the smallest number evenly divisible by each number from 1 to n.</p>

<div>
<p><strong>Example 1:</strong></p>

<pre><strong>Input: </strong><span id="example-input-1-1">
N=3</span>
<strong>Output: </strong><span id="example-output-1"> 6
</pre>


</div>

<div>
<p><strong>Example 2:</strong></p>

<pre><strong>Input: </strong><span id="example-input-1-1">
N=6</span>
<strong>Output: </strong><span id="example-output-1"> 60
</pre>


</div>

```cpp
class Solution{
public:
    long long getSmallestDivNum(long long n){ long long ans = 1;     
    for (long long i = 1; i <= n; i++) 
        ans = (ans * i)/(__gcd(ans, i)); 
    return ans; 
        // code here
    }
};
