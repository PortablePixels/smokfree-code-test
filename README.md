# Smoke Free - Code Test

## The Brief
Produce an API to support a simple webapp game. The game takes a single word or phrase and assigns a score based on the length and correctness.

Single word, if a palindrome the word score is 3 mutliplied by its length.

Phrase, a phrase can be a single word, a sentence or a paragraph. Scored by counting the number of palindromes in the phrase and multiplying that by the total of scored for each palindrome (scored as above).

There is also a top scorers table which shows the top 10 and the last 10 scores.

Single Word:\
*racecar*\
`7 * 3 = 21`

Phrase:\
*I was out in my racecar, which was a Honda civic. My race name is Madam Noon. My real name is Hannah Solos and I like to listen to pop whilst racing.*\
`21 + 15 + 15 + 15 + 12 + 18 + 15 + 9 = 120`\
`120 * 8 = 960`

## Requirements
1. Produce three endpoints
2. Validation returns true/false if a palindrome
3. Scoring returns the score of the submitted phrase or single word
4. Leader board

## API Contracts
GET `/validate/{word}/`\
RESPONSE\
Status Code: `200`\
Body:
```JSON
{
  "word": "racecar",
  "valid": TRUE
}
```
---
POST  `/score`\
REQUEST\
Body:
```JSON
{
  "uid": "8c25fa44-752e-11ec-90d6-0242ac120003",
  "nickname":"Adam",
  "phrase": "I was out in my racecar, which was a Honda civic. My race name is Madam Noon. My real name is Hannah Solos and I like to listen to pop whilst racing."
}
```
RESPONSE\
Status Code: `200`\
Body:
```JSON
{
  "score":960
}
```
---
GET `/leader-board`\
RESPONSE\
Status Code: `200`\
Body:
```JSON
{
"top_scorers":[
  {
    "postion": 1,
    "nickname": "Adam",
    "score": 960,
  },
  {
    "postion": 2,
    "nickname": "Chris",
    "score": 160,
  },
  {
    "postion": 3,
    "nickname": "Adam",
    "score": 60,
  }
],
"last_10":[
  {
    "date": "2022-01-14T10:22Z",
    "nickname": "Adam",
    "score": 60,
  },
  {
    "date": "2022-01-14T9:42Z",
    "nickname": "Chris",
    "score": 160,
  },
  {
    "date": "2022-01-14T9:22Z",
    "nickname": "Adam",
    "score": 960,
  }
 ]
}
```
## Hints
- Don't spend more than 4 hours on this
- Prioritise tasks, complete what you can
- Ensure your code runs IMPORTANT
- Branch when needed use feature branching workflow
- Commit often (At every success) You should have more than two commits
- Meet the requirements
- Ask questions if anything is unclear

## Extension Points
- Validate code with tests
- Validate submissions
- Handle errors appropriately (mising parameters, wrong API request i.e. POST not GET)
- Detect fake submissions i.e. non-words, emojis
- Jest tests across all endpoints
- Store answers in a local DB, make top persist after server restarts.

## Helpers
Create and checkout a feature branch:\
`git checkout -b initials/fancy-branch-name`

Note: LP convention: Your branch name should start with your initials and then a description of your feature (as above).\
Do work in your feature branch, committing early and often:\
`git commit -m "Comment about the commit`
