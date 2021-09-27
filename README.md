## Permutation Cipher:
A cryptographic protocol is when there are two parties Alice and Bob, and Alice wants to send a message to Bob. However, Eve wants to intercept this message but Alice needs to make sure only Bob knows what she wanted to send. 
For this, Alice and Bob meet initially and Alice shares a “key” with Bob. Later, whenever Alice needs to send a message to Bob, she encodes the message (m) that she wants to share by a function E(m). Bob needs to decode this message using a decoding algorithm, and a “key” which Alice and Bob previously shared. More specifically we want D(E(m), k) = m.
Now, Alice uses the encryption which is a permutation map. This means that if ‘a’ is mapped to ‘m’ and ‘b’ is mapped to ‘t’, then the word ‘abaab’ would be ‘mtmmt’. This permutation can be seen as a function f : N -> N where, given the ASCII value of the message alphabet, it outputs the ASCII value of the encrypted alphabet. For simplicity, we restrict out ASCII values from 34 to 122 to include alphabets and symbols (Notice that this sample space is of size 89, a prime. Can you guess why?).

We are going to describe a decryption protocol. For a given key k, the decryption function is given as D(x) = ((x-34)^k mod 89) + 34.
The input will contain a few lines. First line will contain the key k. 
Each of the next lines will contain strings, that need to be decoded and the output given. Note that, space (ASCII 32) stays as is.


### Sample Test Cases:
* Sample Test Case 1:
  * Input:
    ```
    33
    abcdefghijklmnopqrstuvwxyz
    ```
  * Output:
    ```
    @*),+.-0/21436587:9<;>=@?B
    ```
* Sample Test Case 2:
  * Input:
    ```
    15
    N(B &M88;Gja L8 FPjnQDhZQq'zAF
    ```
  * Output: 
    ```
    The password is '<rt4YZ@467z>'
    ```
  
  
  
  
  
##### Designed by:
[Sayak Chakrabarti](mailto:sayak@cse.iitk.ac.in)
