# Wordle Tests

[Wordle Tests](https://link) lists all possible word-guess combinations.

Each line follows the template: `<word1>,<result>,<word2>`

| key      | value                                           |
| -------- | ----------------------------------------------- |
| `word1`  | Base word.                                      |
| `result` | Output of a guess made by `word2` onto `word1`. |
| `word2`  | Guess to be made onto `word1` to get `result`.  |
|          | `*` implies no word gives that result.          |

## Generating Base Words

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

## Generating Possible Results

Similarly, the result of a guess is a subset of all possibilities between `ccccc` to `wwwww`.

Some of them are impossible such as `ccccm`.

Sometimes, some results are not possible for a given word. For example, `abcca` can never have a guess result with `mcccw`.

When generating the tests, all possibilities are considered, even the impossible ones so that there are edge cases in the tests.
