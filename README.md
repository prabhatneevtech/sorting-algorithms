Thanks to a careless technical specialist at Neev, selection sort and quick sort just stopped working.
As a fresher, debug the program with the help of browser developer tools using breakpoints and save the day by fixing the program.

The catch - also document your steps below. 

Name : 


Selection Sort
==============

## Steps

1. I putted the break point at 
	for (var i = 0; i < this.a.length; i++)
       {
 (break point).max = i;
            for (var j = 0; j < i; j++)
            {
                if (this.a[j] < this.a[max])
                    max = i;
            }
            this.a.swapVerbose(i, max);
        }


2. Then I clicked on selection sort button 
3. Then I step over next function (F10)
4. I checked array value
5. I found that inner for loop is not executing 50 times (according to selection it should execute 50 times)
6. Then I changed the value of inner loop  for (var j = 0; j < this.a.length; j++)
7. Then I remove the break point and tried to run the script but still it was not working
8. Then again putted break point and I checked that value of max variable is not proper according to array element.
9. Then I changed at two place 
for (var j = i; j < i; j++)
            {
                if (this.a[j] < this.a[max])
                    max = j;
            }
10. Now its working.

QuickSort
=========

## Steps

1. I putted the break Point

part: function(p, r) {
    var v = this.a[p];
    var i = p; ..............(breakboint)
    var j = r;
    while (true) {
        while (this.a[j] > v) j--;
        while (this.a[i] < v) i++;
        if (i < j)
        {
        this.a.swapVerbose(i, j);
        i++;
        j -= 1;
        } else { 
        return j;
        }
    }
    }

2. I found undefine at index 0

3. I changed this.qsort(0, this.a.length-1);
4. I found that after return statement the pivote it not comming at appropriate position infact pivote is not changing position
5. I added this.a.swapVerbose(p, j); into else condition
6. I found i value is starting from pivote itself (it should be next from pivote)
7. then I changed i=p+1;
8. One more thing is in recurson arry is overlapping 
9. So I changed 
	this.qsort(p, q-1);
        this.qsort(q+1, r);
10. Now its working.
