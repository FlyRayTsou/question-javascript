# question-javascript

## Question1: How does Node.js handle concurrency even after being single-threaded?
Answer: Node.js雖然是sinle-threaded，但是透過非同步，而可以達成處理多個請求。主要是有call stack及event queue。執行程式碼時，會把需要執行的部分丟到call stack並且執行，途中會遇到call api或是setTimeout執行，執行過後，因為不一定會馬上有結果，所以會繼續執行其餘程式碼，當api回應的時候，則把結果丟到event queue。會持續檢查call stack是否為空，若為空，則把event queue丟到call stack並執行。
Reference: 
- http://latentflip.com/loupe/
- https://www.geeksforgeeks.org/if-node-js-is-single-threaded-then-how-to-handles-concurrency/
Update Date: 2024/07/06
