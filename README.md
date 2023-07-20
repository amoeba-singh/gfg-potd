## GFG Problem Of The Day

### 🎉 Announcement
I have created a Git Book that contains all previous editorials for my GFG-POTD solutions. You can visit **[here](https://gl01.gitbook.io/gfg-editorials/)** to access it and refer to my previous solutions. In the future, I intend to establish a contribution flow, where others can contribute their solutions to this Git Book. I would appreciate hearing your thoughts and views on this in the [discussion section](https://github.com/getlost01/gfg-potd/discussions).

----
### Today - 20 July 2023
### Que - Non Repeating Character

The problem can be found at the following link: [Question Link](https://practice.geeksforgeeks.org/problems/non-repeating-character-1587115620/1)

### My Approach

To find the first non-repeating character in a given string `S`, I use an array `cnt` of size 26 to count the occurrences of each character. 
I iterate through the string once to populate the `cnt` array. Then, I traverse the string again to find the first character whose count is equal to 1, indicating it is non-repeating.

### Time and Auxiliary Space Complexity

- **Time Complexity**: `O(N)`, where `N` is the length of the input string `S`.
- **Auxiliary Space Complexity**: `O(1)` (constant space) since the `cnt` array has a fixed size of `26`, which does not depend on the input.

### Code (C++)

```cpp
class Solution {
public:
    char nonrepeatingCharacter(string S) {
        int cnt[26] = {0};

        for (auto ch : S) {
            cnt[ch - 'a']++;
        }

        for (auto ch : S) {
            if (cnt[ch - 'a'] == 1) {
                return ch;
            }
        }

        return '$';
    }
};
```

### Contribution and Support

I always encourage contributors to participate in the discussion forum for this repository.

If you have a better solution or any queries / discussions related to the `Problem of the Day` solution, please visit our [discussion section](https://github.com/getlost01/gfg-potd/discussions). We welcome your input and aim to foster a collaborative learning environment.

If you find this solution helpful, consider supporting us by giving a `⭐ star` to the [getlost01/gfg-potd](https://github.com/getlost01/gfg-potd) repository.


![Total number of repository visitors](https://komarev.com/ghpvc/?username=gl01potdgfg&color=blue&&label=Visitors)
