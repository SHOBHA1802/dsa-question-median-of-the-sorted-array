# dsa-question-median-of-the-sorted-array

Median of 2 Sorted Arrays of Different Size

lass Solution{
    public:
    double MedianOfArrays(vector<int>& array1, vector<int>& array2)
    {
        // Your code goes here
        // vector<int>array3;
        // for(int i=0;i<array1.size();i++){
        //     array3.push_back(array1[i]);
        // }
        // for(int i=0;i<array2.size();i++){
        //     array3.push_back(array2[i]);
        // }
        // sort(array3.begin(),array3.end());
        // int a,b;
        // if((array3.size()+1)%2==0){
        //     for(int i=0;i<array3.size();i++){
        //         a= (array3.size()+1)/2+ceil((array3.size()+1+0.1)*1.0);
        //     }
        //     return a;
        // }
        // if(array3.size()+1%2!=0){
        //     for(int i=0;i<array3.size();i++){
        //         b= (array3.size()+1)/2;
        //     }
        //     return b;
        // }
        
        
        // striver
    //     if(array2.size()<array1.size())return MedianOfArrays(array2,array1);
    //     int n1= array1.size();
    //     int n2= array2.size();
    //     int low=0,high=n1;
    //     while(low<=high){
    //         int cut1=(low+high)>>1;
    //         int cut2=(n1+n2)/2-cut1;
    //         int left1= cut1;
    //         if(left1==0){
    //             left1= INT_MIN;
    //         }
    //         else{
    //             left1=array1[cut1-1];
    //         }
    //         int left2=cut2;
    //         if(left2==0){
    //             left2=INT_MIN;
                
    //         }
    //         else{
    //             left2=array2[cut2-1];
    //         }
    //         int right1=cut1;
    //         if(right1==n1){
    //             right1=INT_MAX;
                
    //         }
    //         else{
    //           right1= array1[cut1];
    //         }
    //         int right2=cut2;
    //         if(right2==n2){
    //             right2=INT_MAX;
                
    //         }
    //         else{
    //             right2 = array2[cut2];
    //         }
    //         if(left1<=right2 && left2<=right1){
    //             if((n1+n2)%2==0){
    //                 return (max(left1,left2)+min(right1,right2))/2;
    //             }
    //             else{
    //                 return max(left1,left2);
    //             }
    //         }
    //       else if(left1>right2){
    //             high=cut1-1;  
    //             }
    //             else{
    //                 low=cut1+1;
    //             }
                
            
    //     }
    //     return 0;
        
    
    // }
    if(array2.size()<array1.size())return MedianOfArrays(array2,array1);
        int n1= array1.size();
        int n2= array2.size();
        int low=0,high=n1;
        while(low<=high){
            int cut1=(low+high)>>1;
            int cut2=(n1+n2+1)/2-cut1;
            int left1= cut1==0 ?INT_MIN:array1[cut1-1];
            int left2=cut2==0 ?INT_MIN :array2[cut2-1];
            int right1=cut1==n1 ?INT_MAX :array1[cut1];
            int right2=cut2==n2 ?INT_MIN :array2[cut2];
           
            if(left1<=right2 && left2<=right1){
                if((n1+n2)%2==0){
                    return (max(left1,left2)+min(right1,right2))/2.0;
                }
                else{
                    return max(left1,left2);
                }
            }
           else if(left1>right2){
                high=cut1-1;  
                }
                else{
                    low=cut1+1;
                }
                
            
        }
        return 0.0;
        
    
    }
};

