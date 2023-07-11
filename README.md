# ai-story-telling

The provided Python code performs the following actions:

It opens a file named "story.txt" in read mode using the `open()` function. The file is opened within a context manager (with statement) to ensure proper handling and automatic closing of the file after it is used. The contents of the file are read and stored in the story variable.

It initializes an empty set called words. This set will be used to store unique words found in the story.

It initializes the `start_of_word` variable with the value -1. This variable will keep track of the starting index of a word enclosed within "<" and ">".

Two variables `target_start` and `target_end` are set to "<" and ">", respectively. These variables represent the start and end characters used to enclose words that need to be replaced.

The code enters a loop that iterates over each character in the story string using the `enumerate()` function, which provides both the index and the character itself.

Inside the loop, it checks if the current character is equal to target_start ("<"). If it is, it sets the `start_of_word` variable to the current index, indicating the beginning of a word.

It checks if the current character is equal to target_end (">") and if start_of_word is not equal to -1. This condition ensures that a word has been started and not already ended. If both conditions are met, it means a complete word has been found, so it extracts the word from the story string using slicing (story[start_of_word: i + 1]) and adds it to the words set using the `add()` method. Then, it resets the start_of_word variable to -1 to mark the end of the current word.

After the loop, an empty dictionary called answers is initialized. This dictionary will store the user's input for each word found in the story.

Another loop is used to iterate over each word in the words set.

Inside this loop, it prompts the user to enter a word for the current word using the `input()` function. The prompt includes the current word as part of the message. The user's input is stored in the answer variable.

It adds a key-value pair to the answers dictionary, where the word found in the story is the key, and the user's input is the value.

Once the user has provided inputs for all the words in the story, another loop is used to iterate over each word in the words set.

Inside this loop, it replaces each occurrence of the current word in the story string with the corresponding value from the answers dictionary using the `replace()` method. The updated story string is reassigned to the story variable.

Finally, it prints the modified story string, which now contains the original story with the user's provided words replacing the placeholder words enclosed within "<" and ">".
