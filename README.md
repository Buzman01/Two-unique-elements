# Two-unique-elements
#include<bits/stdc++.h>
#include<algorithm>
using namespace std;
int main()
{
    /*
    N : stores the length of array
    i : used to iterate through the array
    j : used to iterate through the array
    product : used to store the maximum product
    */
    int N,i,j,product;
    cout << "Enter length of array" << endl;
    cin >> N; // Taking array length as input
    vector<int> arr(N); // Stores array elements
    cout << "Enter array elements" << endl;
    for(i=0;i<N;i++) // Loop to take array elements as input
    {
        cin >> arr[i];
    }
    product=INT_MIN; // initialising product to minimum possible integer
    for(i=0;i<N;i++) // loop to get the first element of a pair
    {
        for(j=i+1;j<N;j++) // loop to get the second element of a pair
        {
            product=max(product,(arr[i]*arr[j])); // finding the maximum product of all possible pairs
        }
    }
    cout << "Maximum product is " << product; 
    return 0;
}

//Approach 2; The idea here is to find the two elements having largest magnitude and two elements having smallest magnitude using sorting. Generally, there are two cases possible in an array :

#include<bits/stdc++.h>
#include<algorithm>
using namespace std;
int main()
{
    /*
    N : stores the length of array
    i : Used to iterate through the array
    product : stores the maximum product
    */
    int N,i,product;
    cout << "Enter length of array" << endl;
    cin >> N; // Taking length of array as input
    vector<int> arr(N); // Stores array elements
    cout << "Enter array elements" << endl;
    for(i=0;i<N;i++) // Loop to take array elements as input
    {
        cin >> arr[i];
    }
    sort(arr.begin(),arr.end()); // sorting the array
    product=max((arr[0]*arr[1]),(arr[N-1]*arr[N-2])); // finding the maximum of product of two largest elements and two smallest elements
    cout << "Maximum product is " << product;
    return 0;
}
