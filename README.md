# Wordle Tests

[Wordle Tests](https://github.com/yukosgiti/wordle-tests) is a set of comprehensive tests for a guesser function for the game Wordle.

---
## [tests.txt](https://github.com/yukosgiti/wordle-tests/blob/main/data/tests.txt)
Each line follows the template: `<word1>,<word2>,<result>`

|  |                                            |
| -------- | ----------------------------------------------- |
| `word1`  | Base word.                                      |
| `word2`  | Guess to be made onto `word1` to get `result`.  |
| `result` | Output of a guess made by `word2` onto `word1`. |



---

## [base_words.txt](https://github.com/yukosgiti/wordle-tests/blob/main/data/base_words.txt)
Each line follows the template: `<word>`

A 5 letter word can consist of 1-5 unique letters. Below, you can find all 52 lexicographically ordered possibilities. Every 5 letter word after lexicographically ordering is one of the values below.

`Class` specifies counts of each unique letter.

| ULC | Class         | Values                                                                                                                                |
| --- | ------------- | ------------------------------------------------------------------------------------------------------------------------------------- |
| 1   | `<5,0,0,0,0>` | `aaaaa`                                                                                                                               |
| 2   | `<4,1,0,0,0>` | `aaaab`, `aaaba`, `aabaa`, `abaaa`, `abbbb`                                                                                           |
| 2   | `<3,2,0,0,0>` | `aaabb`, `aabab`, `aabba`, `aabbb`, `abaab`, `ababa`, `ababb`, `abbaa`, `abbab`, `abbba`                                              |
| 3   | `<3,1,1,0,0>` | `aaabc`, `aabac`, `aabca`, `abaac`, `abaca`, `abbbc`, `abbcb`, `abcaa`, `abcbb`, `abccc`                                              |
| 3   | `<2,2,1,0,0>` | `aabbc`, `aabcb`, `aabcc`, `ababc`, `abacb`, `abacc`, `abbac`, `abbca`, `abbcc`, `abcab`, `abcac`, `abcba`, `abcbc`, `abcca`, `abccb` |
| 4   | `<2,1,1,1,0>` | `aabcd`, `abacd`, `abbcd`, `abcad`, `abcbd`, `abccd`, `abcda`, `abcdb`, `abcdc`, `abcdd`                                              |
| 5   | `<1,1,1,1,1>` | `abcde`                                                                                                                               |


\*_ULC: Unique Letter Count_

---

## [possible_results.txt](https://github.com/yukosgiti/wordle-tests/blob/main/data/possible_results.txt)
Each line follows the template: `<result>`

The result is all possibilities between `ccccc` to `wwwww`. (Also contains invalid results.)

---

## [impossible_results.txt](https://github.com/yukosgiti/wordle-tests/blob/main/data/impossible_results.txt)
Each line follows the template: `<word>,<result>`

Not all possible results are valid. For example it is impossible to get `ccccm` as a result. 

Sometimes, some results are not possible for a given word. For example, `abcca` can never have a guess result with `mcccw`.

So each line can be interpreted as there are no matches for `word` to obtain `result`.

