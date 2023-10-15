![[unnamed (47).gif]]

The trie (pronounced ‘try’), or prefix tree, is a kind of search tree. A trie stores data in steps where each step is a node in the trie. Tries are often used to store words for quick lookups, such as a word auto-complete feature.  
  
Each node in a language trie contains one letter of a word. You follow the branches of a trie to spell a word, one letter at a time. The steps begin to branch off when the order of the letters diverges from the other words in the trie, or when a word ends. Each node contains a letter (data) and a boolean that indicates whether the node is the last node in a word.  
  
Look at the image and you can form words. Always start at the root node at the top and work down. The trie shown here contains the words ball, bat, doll, do, dork, dorm, send, sense. A restricted tree that lets you restrict how and where data can be stored within them and is the news and specific situations so don't focus on it too much for the interview  
  
Tri-store letter of the alphabet and characters you can carefully construct words by traversing the try in certain ways it is also known as a prefix tree probably in discreet math  
  
The try has a root node that is empty usually a blank value like an empty string or null it also has a set of references in the node that are in an array and are null at the beginning of the try existence  
  
What can be slowly filled with references to other nodes  
  
So let's say we're creating a try to store words that start with d the root would contain an array that contains a reference to a node containing the character d which would signify the start of the word then the d would have its own array containing references pointing to all characters in the alphabet which serve as the first two characters of a word in the English dictionary so it would store something like a da or a DE or whatever else words start with certain letters starting with d  
  
This will continue to repeat again for the next letter  
  
Until we reach the flag that you set to stop  
  
Tries are probably used in Grammarly and pro rite aid  
  
Also, autocorrect  
  
A trie is an array with a tree in it