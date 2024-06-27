## Computer Science
---
*   Essentially, computer programming is about taking some input and creating some output - thus solving a problem. What happens in between the input and output, what we could call _a black box,_ is the focus of this course.

![Black box with input and output](cs50Week0Slide38.png "Black box with input and output")

*   For example, we may need to take attendance for a class. We could use a system called _unary_ to count, one finger at a time.
*   Computers today count using a system called _binary_. It’s from the term _binary digit_ that we get a familiar term called _bit_. A _bit_ is a zero or one: on or off.
*   Computers only speak in terms of zeros and ones. Zeros represent _off._ Ones represent _on._ Computers are millions, and perhaps billions, of transistors that are being turned on and off.
*   If you imagine using a light bulb, a single bulb can only count from zero to one.
*   However, if you were to have three light bulbs, there are more options open to you!
*   Using three light bulbs, the following could represent zero:
    
        0 0 0
    
*   Similarly, the following would represent one:
    
        0 0 1
    
*   By this logic, we could propose that the following equals two:
    
        0 1 0
    
*   Extending this logic further, the following represents three:
    
        0 1 1
    
*   Four would appear as:
    
        1 0 0
    
*   We could, in fact, using only three light bulbs count as high as seven!
    
        1 1 1
    
*   As a heuristic, we could imagine that the following values represent each possible place in our _binary digit_:
    
        4 2 1
    
*   Computers use ‘base-2’ to count. This can be pictured as follows:
    
        2^2  2^1  2^0
        4    2    1
    
*   Therefore, you could say that it would require three bits (the four’s place, the two’s place, and the one’s place) to represent a number as high as seven.
*   Computers generally use eight bits (also known as a _byte_) to represent a number. For example, `00000101` is the number 5 in _binary_. `11111111` represents the number 255.

## ASCII
---
*   Just as numbers are binary patterns of ones and zeros, letters are represented using ones and zeros too!
*   Since there is an overlap between the ones and zeros that represent numbers and letters, the _ASCII_ standard was created to map specific letters to specific numbers.
*   For example, the letter `A` was decided to map to the number 65. `01000001` represents the number 65 in binary.
*   If you received a text message, the binary under that message might represent the numbers 72, 73, and 33. Mapping these out to ASCII, your message would look as follows:
    
        H   I   !
        72  73  33
    
*   Thank goodness for standards like ASCII that allow us to agree upon these values!
*   Here is an expanded map of ASCII values:

![ASCII map](cs50Week0Slide93.png "ASCII map")

*   If you wish, you can learn more about [ASCII](https://en.wikipedia.org/wiki/ASCII).
*   Since binary can only count up to _255_ we are limited to the number of characters represented by ASCII.

## Unicode
---
*   As time has rolled on, there are more and more ways to communicate via text.
*   Since there were not enough digits in binary to represent all the various characters that could be represented by humans, the _Unicode_ standard expanded the number of bits that can be transmitted and understood by computers. Unicode includes not only special characters, but emoji as well.
*   There are emoji that you probably use every day. The following may look familiar to you:

![emoji](cs50Week0Slide103.png "emoji")

*   Computer scientists faced a challenge when wanting to assign various skin tones to each emoji to allow the communication to be further personalized. In this case, the creators and contributors of emoji decided that the initial bits would be the structure of the emoji itself, followed by skin tone.
*   For example, the unicode for a generic thumbs up is `U+1F44D`. However, the following represents the same thumbs up with a different skin tone: `U+1F44D U+1F3FD`.
*   More and more features are being added to the Unicode standard to represent further characters and emoji.
*   If you wish, you can learn more about [Unicode](https://en.wikipedia.org/wiki/Unicode).
*   If you wish, you can learn more about [emoji](https://en.wikipedia.org/wiki/Emoji).

## Representation
---
*   Zeros and ones can be used to represent color.
*   Red, green, and blue (called `RGB`) is a combination of three numbers.

![red green blue boxes](cs50Week0Slide118.png "red green blue boxes")

*   Taking our previously used 72, 73, and 33, which said `HI!` via text, would be interpreted by image readers as a light shade of yellow. The red value would be 72, the green value would be 73, and the blue would be 33.

![yellow box](cs50Week0Slide120.png "yellow box")

*   Further, zeros and ones can be used to represent images, videos, and music!
*   Images are simply collections of RGB values.
*   Videos are sequences of many images that are stored together, just like a flipbook.
*   Music can be represented through MIDI data.