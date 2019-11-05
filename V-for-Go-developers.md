<table>
<tr><td colspan="2" align="center">Hello World</td></tr>
<tr>
<td>
<pre class="highlight highlight-source-v">
package main
import "fmt"
func main() {
  fmt.Println("Hello World!")
}
</pre>
</td>
<td valign="top">
<pre>
fn main() {
  println('Hello World!')
}
</pre>
</td>
</tr>


<tr><td colspan="2" align="center">Slice initialization</td></tr>
<tr>
<td>
<pre>
numbers := []int{1, 2, 3, 4}
</pre>
</td>
<td valign="top">
<pre>
numbers := [1, 2, 3, 4]
</pre>
</td>
</tr>

<tr><td colspan="2" align="center">Add an element to a slice</td></tr>
<tr>
<td>
<pre>
numbers = append(numbers, 5)
</pre>
</td>
<td valign="top">
<pre>
numbers << 5
</pre>
</td>
</tr>

<tr><td colspan="2" align="center">Printing a slice</td></tr>
<tr>
<td>
<pre>
fmt.Println(numbers)
</pre>
</td>
<td valign="top">
<pre>
println(numbers)
</pre>
</td>
</tr>


<tr><td colspan="2" align="center">Filtering a vector</td></tr>
<tr>
<td>
<pre>
even := make([]int, 0)
for _, num := range numbers {
  if num % 2 == 0 {
    even = append(even, num)
  }
}

</pre>
</td>
<td valign="top">
<pre>
even := numbers.filter(it % 2 == 0)
</pre>
</td>
</tr>



<tr><td colspan="2" align="center">Reading a file</td></tr>
<tr>
<td>
<pre>
import (
    "io/ioutil"
    "log"
)
b, err := ioutil.ReadFile(path)
if err != nil {
        log.Println(err)
}
text := string(b)
</pre>
</td>
<td valign="top">
<pre>
import os
text := os.read_file(path)or{
  eprintln(err)
}
</pre>
</td>
</tr>




</table>

