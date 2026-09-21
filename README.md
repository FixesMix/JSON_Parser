This is intended for use with .docx only. Please note that CHAPTER, START, NODE, and NEXT_CHAPTER must not be omitted.
The format is as follows:

1. Chapter must begin with keyword "CHAPTER:"
2. The start of a chapter ("START:") must appear after "CHAPTER:", and never before
3. Keyword "NODE:" must be used to signal a position change. Position change should be initiated at the start of every chapter, and re-established at every choice (given said choice changes character environment)
4. Keyword "NEXT_CHAPTER:" is a field on the current node that tells the parser where to go next. Keyword "CHAPTER" is still required on the next node

5. "NEXT:" continues without a choice requirement, "SETS_FLAG:" is a choice to be remembered

Example:
```
CHAPTER: 1
TITLE: New Chapter
START: Forest

NODE: Forest
NARRATOR: It's very cold here :(
NARRATOR: The man takes a turn on the path and looks to his left. He finds a cave.
CHOICE: Go to cave -> Cave
CHOICE: Stay on the path -> Forest

NODE: Cave
NARRATOR: It's very dark in here :(
NEXT_CHAPTER: 2

CHAPTER: 2
TITLE: Next New Chapter
START: Cave

NODE: Cave
... And so on and so forth
```
