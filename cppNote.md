C++
===

### stringstreams 
+ https://www.dreamincode.net/forums/topic/95826-stringstream-tutorial/
    -  stringstream works essentially the same as an input/output file stream. You need the preprocessor directive #include <sstream>, declare a stringstream just like an fstream
    - It uses both forms of the istream getline member. Both of them take characters from the stream, copy them into a char array and terminate them with a '\0'.
    - The first one reads up to n-1 characters or until it reaches a newline or eof:
    ```c++
    istream& getline (char* s, streamsize n );
    ```
    -The second one reads up to n-1 characters or until it reaches the character specified as 'delim' or eof:
    ```c++
    istream& getline (char* s, streamsize n, char delim );
    ```

+ difference-between-istringstream-ostringstream-and-stringstream
  - https://stackoverflow.com/questions/3292107/whats-the-difference-between-istringstream-ostringstream-and-stringstream-w
  - https://doc.bccnsoft.com/docs/cppreference_en/cppsstream/all.html
+ auto
  - https://stackoverflow.com/questions/29859796/c-auto-vs-auto
+ https://thispointer.com/c-how-to-check-if-a-set-contains-an-element-setfind-vs-setcount/
  - Both set::find() and set:: count() helps to check the existence of an element in set. But why 2 different method for same thing ?
