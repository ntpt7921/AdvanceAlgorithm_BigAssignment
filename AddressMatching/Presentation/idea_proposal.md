% Some ideas I think worth considering
% 13/10/2024

# Approximate string matching (fuzzy matching)

## Edit distance

- yes, maybe that one
- some what easily calculated (with dynamic programming) -> O(mn)
- many types, Levenshtein for now

## Fuzzy matching

- current test
    - can see that this is feasible (within time limit)
    - can deal with deteriorated string
    - can deal with elements out of order
    - straight forward implementation (cheating by copying library)

- plan
    - impl algo for edit distance between string
    - impl min distance substring matching
    - result is highly likely to be favorable

# Multi-phase approach to classification

- trie is fast (really fast) after it is built, but only for exact match

- fuzzy matching is slower (within reason), but can not guarantee performance metrics

- so combine them, so we have resilience and speed
    - phase 1: matching by trie, if match then finish
    - phase 2: matching by fuzzy

# Heuristic element segmentation

- address have useless part: (12/23 Đường CMT8, Khu phố 4,) P 17, Quận Bình Thạnh, TPHCM

- we need 3 element: province, district and ward.
    - assume they are at the end
    - each element take about 3 words
    - then separate the useful part by:
        - taking ~9 words at the end
        - combined with info of separator (',')

# Frame work for management

- need timing/interrupt for long-standing task
- need logging for success/fail case -> to be used for further analysis
- decide when and how to use fuzzy/trie
