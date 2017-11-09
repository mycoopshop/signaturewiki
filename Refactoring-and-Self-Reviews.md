Remove dependencies on the variable which caused the bug (questionId === ???)

Replace the logic with an array of all states

Use that array to generate other arrays of actions (function calls) and metadata (HTML/CSS)

Reference those in templates rather than using conditional logic