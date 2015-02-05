# Trying Trie Data Structure

I just wanted to know if it fits my needs for a certain project. I've found a dictionary of reasonable size and tried to store in the trie. Well, long story short, it didn't meet my needs.

It shows blazing speed while in cache, or, in the opposite when cahce is no longer the issue. But my data size is about tens of thouthands of records and this is exactly the size, when it fits perfectly in level 2 cache of i5 as a hash table or binary tree.

Here's some numbers I measured:

1000 loop cycles reading about 50 000 records

                    memory          R time
    trie 2          53 M            20 s.           
    trie 4          36 M            11 s.
    trie 16         46 M                8 s.
    trie 128        150 M           21 s.
    
    hash            5 M                     14 s.
    R/B tree        5 M                 44 s.
    
    low_bound       3.1 M               74 s.
    vector          3.1 M           21 000 s.
    string          3.7 M           20 000 s.


10 000 loop cycles reading 5000 records

    trie 2          4 M                     4 s.
    trie 4          4 M                     4 s.
    trie 16         7 M                     4 s.
    trie 128        11 M            3 s.
    
    hash            1 M                     11 s.
    R/B tree        1 M                 31 s.
