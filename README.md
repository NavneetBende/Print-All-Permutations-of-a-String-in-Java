# Print-All-Permutations-of-a-String-in-Java

Print All Permutations of a String in Java
Given a string str, the task is to print all of str permutations. A permutation is an arrangement of all or part of a set of objects in the order in which they are arranged. For example, the words ‘bat’ and ‘tab’ are two different permutations (or arrangements) of a similar three-letter word.

Example :

Input : ABC
Output : ABC ACB BCA BAC CAB CBA
Print All Permutations of a String in Java
Method 1(Using Recursion) :
Create a recursive function say printPermute(string s, int l, int r), and pass string along with starting index of the string and the ending index of the string.
Base condition will be if(l==r) then print the s.
Otherwise, run a loop from [l, r]
And, swap(s[l], s[i])
Call printPermute(s, l+1, r) function
And again swap(s[l], s[i]) to backtrack.
Print All Permutations of a String in Java
Code to print All Permutations of a String in Java
Run
public
class Main {
    // Function to print all the permutations of str
    static void printPermutn(String str, String ans) {

        // If string is empty
        if (str.length() == 0) {
            System.out.print(ans + " ");
            return;
        }
        for (int i = 0; i < str.length(); i++) {

            // ith character of str
            char ch = str.charAt(i);

            // Rest of the string after excluding the ith character
            String r = str.substring(0, i) + str.substring(i + 1);

            // Recurvise call
            printPermutn(r, ans + ch);
        }
    }

    // Driver code
    public
    static void main(String[] args) {
        String s = "abb";
        printPermutn(s, "");
    }
}
Output :


ABC ACB BCA BAC CAB CBA
Related Pages
Finding Number of times x digit occurs in a given input
 
Finding number of integers which has exactly x divisors
 
Smallest element in an array

Power of a Number

Largest element in an array

Method 2
Create a recursive function that prints out different permutations. Create a boolean array of size ’26’ that accounts for the character that is being used. The recursive call will be made if the character has not been used. Otherwise, don’t make any call. When the passed string is empty, the programme will terminate.

Run
public class Main {
    static void printDistinctPermutn(String str, String ans) {
        // If string is empty
        if (str.length() == 0) {
            // print ans
            System.out.print(ans + " ");
            return;
        }
        // Make a boolean array of size '26' which stores false by default and make true
        // at the position which alphabet is being used
        boolean alpha[] = new boolean[26];
        for (int i = 0; i < str.length(); i++) {
        // ith character of str
        char ch = str.charAt(i);

        // Rest of the string after excluding
        // the ith character

        String ro = str.substring(0, i) + str.substring(i + 1);
        if (alpha[ch - 'a'] == false) 
        printDistinctPermutn(ro, ans + ch);
        alpha[ch - 'a'] = true;
     }
  }

  // Driver code
  public
      static void main(String[] args) {
      String s = "abc";
      printDistinctPermutn(s, "");
    }
  }
Output
abc acb bac bca cab cba
