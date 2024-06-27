## [Algorithms](Week%203%20-%20Algorithms.md)
---
*   Problem-solving is central to computer science and computer programming.
*   Imagine the basic problem of trying to locate a single name in a phone book.
*   How might you go about this?
*   One approach could be to simply read from page one to the next to the next until reaching the last page.
*   Another approach could be to search two pages at a time.
*   A final and perhaps better approach could be to go to the middle of the phone book and ask, “Is the name I am looking for to the left or to the right?” Then, repeat this process, cutting the problem in half and half and half.
*   Each of these approaches could be called algorithms. The speed of each of these algorithms can be pictured as follows in what is called [_big-O notation_](Big%20O,%20Ω%20and%20Θ%20notations.md):

![big o notation](cs50Week0Slide141.png "big o notation")

Notice that the first [algorithm](Week%203%20-%20Algorithms.md), highlighted in red, has a big-O of `n` because if there are 100 names in the phone book, it could take up to 100 tries to find the correct name. The second algorithm, where two pages were searched at a time, has a big-O of ‘n/2’ because we searched twice as fast through the pages. The final algorithm has a big-O of log2n as doubling the problem would only result in one more step to solve the problem.

## Pseudocode
---
*   The ability to create _pseudocode_ is central to one’s success in both this class and in computer programming.
*   Pseudocode is a human-readable version of your code. For example, considering the third algorithm above, we could compose pseudocode as follows:
    
        1  Pick up phone book
        2  Open to middle of phone book
        3  Look at page
        4  If person is on page
        5      Call person
        6  Else if person is earlier in book
        7      Open to middle of left half of book
        8      Go back to line 3
        9  Else if person is later in book
        10     Open to middle of right half of book
        11     Go back to line 3
        12 Else
        13     Quit
    
*   Pseudocoding is such an important skill for at least two reasons. First, when you pseudocode before you create formal code, it allows you to think through the logic of your problem in advance. Second, when you pseudocode, you can later provide this information to others that are seeking to understand your coding decisions and how your code works.
*   Notice that the language within our pseudocode has some unique features. First, some of these lines begin with verbs like _pick up,_ _open,_ _look at._ Later, we will call these _functions_.
*   Second, notice that some lines include statements like `if` or `else if.` These are called _conditionals_.
*   Third, notice how there are expressions that can be stated as _true_ or _false,_ such as “person is earlier in the book.” We call these _boolean expressions_.
*   Finally, notice how these statements like “go back to line 3.” We call these _loops_.
*   These building blocks are the fundamentals of programming.
*   In the context of _Scratch_, which is discussed below, we will use each of the above basic building blocks of programming.
## Artificial Intelligence
---
*   Consider how we can utilize the building blocks above to start creating our own artificial intelligence. Look at the following pseudocode:
    
        If student says hello
            Say hello back
        Else if student says goodbye
            Say goodbye back
        Else if student asks how you are
            Say you're well
        Else if student asks why 111 in binary is 7 in decimal
        ...
    
    Notice how just to program a handful of interactions, many lines of code would be required. How many lines of code would be required for thousands or tens of thousands of possible interactions?
    
*   `large language models` look at patterns in large blocks of language. Such language models attempt to create a best guess of what words come after one another or alongside one another.
*   As very useful in many avenues of life and work, we stipulate that the utilization of AI-based software other than CS50’s own is _not reasonable_.
*   CS50’s own AI-based software tool called [CS50 Duck](https://cs50.ai) is an AI helper that you can use during this course. It will help you, but not give away the entire answers to the course’s problems.