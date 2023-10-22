<h1>ExpNo 7 : Solve Cryptarithmetic Problem,a CSP(Constraint Satisfaction Problem) using Python</h1> 
<h3>Name: Saravanan N</h3>
<h3>Register Number/Staff Id: TSML006</h3>
<H3>Aim:</H3>
<p>
    To solve Cryptarithmetic Problem,a CSP(Constraint Satisfaction Problem) using Python
</p>
<h3>Theory:</h3>
Input and Output
Input:
This algorithm will take three words.
             B A S E
             B A L L
           ----------
           G A M E S

Output:
It will show which letter holds which number from 0 – 9.
For this case it is like this.

              B A S E                         2 4 6 1
              B A L L                         2 4 5 5
             ---------                       ---------
            G A M E S                       0 4 9 1 6
Algorithm
For this problem, we will define a node, which contains a letter and its corresponding values.

isValid(nodeList, count, word1, word2, word3)

Input − A list of nodes, the number of elements in the node list and three words.

Output − True if the sum of the value for word1 and word2 is same as word3 value.

Begin
   m := 1
   for each letter i from right to left of word1, do
      ch := word1[i]
      for all elements j in the nodeList, do
         if nodeList[j].letter = ch, then
            break
      done
      val1 := val1 + (m * nodeList[j].value)
      m := m * 10
   done

   m := 1
   for each letter i from right to left of word2, do
      ch := word2[i]
      for all elements j in the nodeList, do
         if nodeList[j].letter = ch, then
            break
      done

      val2 := val2 + (m * nodeList[j].value)
      m := m * 10
   done

   m := 1
   for each letter i from right to left of word3, do
      ch := word3[i]
      for all elements j in the nodeList, do
         if nodeList[j].letter = ch, then
            break
      done

      val3 := val3 + (m * nodeList[j].value)
      m := m * 10
   done

   if val3 = (val1 + val2), then
      return true
   return false
End
