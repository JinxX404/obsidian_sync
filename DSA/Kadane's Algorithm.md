الجوريزم بنستخدمه علشان نجيب ال max subarray 
الsubarray هي جزء من الاراي contiguous 
مثلا الاراي
(1,2,3,4)
يبقي الsubarrays بتوعها 
1 
1,2
1,2,3
1,2,3,4
2
2,3
2,3,4 
وهكذا

عايز اجيب اكبر مجموع subarray فيهم 

الحل التقليدي اني هستخدم 3 nested loops وهتكون O(n^3)

----
الالجورزم ده هيحللنا المشكله في linear time O(n)

The idea of ****Kadane’s algorithm**** is to maintain a variable ****max_ending_here**** that stores the maximum sum contiguous subarray ending at current index and a variable ****max_so_far**** stores the maximum sum of contiguous subarray found so far, Everytime there is a positive-sum value in ****max_ending_here**** compare it with ****max_so_far**** and update ****max_so_far**** if it is greater than ****max_so_far****.

![[Pasted image 20240708232903.png]]
بيكون معايا 2 فاريبل curSum و maxSum

الmaxsum هيشيل اكبر ماكس وصلناله 
والcursum بيشيل الsum بتاع الsubarray الي ماسكينها حاليا

لو الcursum بتاعنا بقي سالب بنعمله ديسكارد 

- The subarray with negative sum is discarded (__by assigning max_ending_here = 0 in code__).
- We carry subarray till it gives positive sum.

```psudocode
- Initialize the variables max_so_far = INT_MIN and max_ending_here = 0
- Run a for loop from 0 to N-1 and for each index i: 
    - Add the arr[i] to max_ending_here.
    - If  max_so_far is less than max_ending_here then          update max_so_far  to max_ending_here
    - If max_ending_here < 0 then update                                max_ending_here = 0 
- Return max_so_far

```

بنمسك العنصر الحالي ونضيفه علي الcursum وبنسال هل المجموع الي معايا حاليا اكبر من الmaxsum الي جبته قبل كده؟
لو اكبر منه هخزنه جوه الmax  , لو مش اكبر ف انا معايا الماكس مجتش جمبه

وبعدين بسال هل الcurrsum اقل من زيرو؟ 
بنتشيك اذا كان سالب ولا لا
 علشان لو سالب هنعمله ديسكارد لان السالب مش هيفيدنا فحاجه في الmax sum 


https://www.geeksforgeeks.org/largest-sum-contiguous-subarray/

