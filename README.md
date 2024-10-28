# C-Program-to-Check-if-String-is-Pangram
// A C Program to check if the given string is a pangram or not
#include <stdbool.h>
#include <stdio.h>
#include <string.h>

// Returns true if the string is a pangram, else false
bool checkPangram(char str[]) {
    // Create a hash table to mark the characters present in the string
    bool mark[26];
    for (int i = 0; i < 26; i++)
        mark[i] = false;

    // Traverse all characters
    size_t size = strlen(str);
    for (int i = 0; i < size; i++) {
        // If uppercase character, subtract 'A' to find index
        if ('A' <= str[i] && str[i] <= 'Z')
            mark[str[i] - 'A'];
        // If lowercase character, subtract 'a' to find index
        else if ('a' <= str[i] && str[i] <= 'z')
            mark[str[i] - 'a'];
        // If this character is other than English lowercase and uppercase characters, skip it
        else
            continue;
    }

    // Return false if any character is unmarked
    for (int i = 0; i <= 25; i++) {
        if (mark[i] == false)
            return false;
    }

    // If all characters were present, it's a pangram
    return true;
}

// Driver Program to test above functions
int main() {
    char str[] = "The quick brown fox jumps over the lazy dog";
    if (checkPangram(str) == true)
        printf("%s is a pangram\n", str);
    else
        printf("%s is not a pangram\n", str);
    return 0;
}
