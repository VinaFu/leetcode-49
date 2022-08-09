# leetcode-49


1) class Solution: dict/ hash_table/ map

        def groupAnagrams(self, strs: List[str]) -> List[List[str]]:
            dict = {}
            for val in strs:    
                    # decide the key and value. in this case, since "aet" can map to varied value, such as "eat", "ate"
                    # Since the key show be unique, "aet" should be the key
                    # key cann't be list, so change it into str.
                key = "".join(sorted(val))  
                    # define the key
                    # sorted()+ other functions: join // sort only mutate the original one.
                if key not in dict:      
                        # build the dict, and from now on, only quote dict 
                    dict[key] = [val]    
                        # build the first element
                else:
                    dict[key].append(val)   
                        # same element put in the same box
            return list(dict.values())     
                        # values is a function itself, so need a bracket behind it.

2) bruce force

            # def groupAnagrams(strs):
          #         dict = {}
          #         for i in range(len(strs)):
          #                 key = list(strs[i])
          #                 key.sort()
          #                 key = tuple(key)
          #                 # print(key)    
          #                 if key not in dict:
          #                         dict[key] = [strs[i]] 
          #                         # aet - eat
          #                 else:
          #                         dict[key].append(strs[i])
          #                         # aet - tea
          #                         # append to specific key - [[], []]
          #         ans = []
          #         for key, value in dict.items():
          #                 ans.append(value)
          #         return ans


          # strs = ["eat","tea","tan","ate","nat","bat"]
          # print(groupAnagrams(strs))





