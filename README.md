![image](https://user-images.githubusercontent.com/109466091/234633044-a2d5aa17-4fe5-42b4-9b66-87a641f346ff.png)
class Solution {
public:

    void findcombination(vector<int>&arr,vector<vector<int>>&ans , vector<int>ds, int index, int target ){
        if(target==0){
          ans.push_back(ds); 
          return ; 
        }
    
      for(int i=index; i<arr.size(); i++){

        if(i>index && arr[i]==arr[i-1]) continue; 

          if(arr[i]>target) break; 

          ds.push_back(arr[i]); 

          findcombination(arr, ans, ds, i+1,target-arr[i]);
          ds.pop_back(); 
      }
    
}

    vector<vector<int>> combinationSum2(vector<int>& candidates, int target) {
        
        sort(candidates.begin(), candidates.end()); 

        vector<vector<int>>ans; 

        vector<int>ds; 

        findcombination(candidates, ans, ds, 0, target); 

        return ans; 
    }
};
