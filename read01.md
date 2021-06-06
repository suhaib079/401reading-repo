# Pain and Suffering:

 accelerated learning environment is great, but it does come at a price that is felt in all spheres of life: physical, mental, and emotional.That price is pain, the pain of growth.


- The pain that I’ll experience during this course is no exception; most times it won’t feel good. I won’t feel good.

- Suffering is pain without purpose. Pain with no higher goal. Pain with no dreams, no ambition, no aspiration.

# A beginner's guide to Big O Notation:
- Big O notation is used in Computer Science to describe the performance or complexity of an algorithm.
- the best way to understand Big O thoroughly was to produce some examples in code. So, below are some common orders of growth along with descriptions and examples where possible.

### O(1):
- O(1) describes an algorithm that will always execute in the same time (or space) regardless of the size of the input data set.
bool IsFirstElementNull(IList<String> elements)
{
    return elements[0] == null;
}

### O(N):
- O(N) describes an algorithm whose performance will grow linearly and in direct proportion to the size of the input data set.
bool ContainsValue(IEnumerable<string> elements, string value)
{
    foreach (var element in elements)
    {
        if (element == value) return true; 
    }     
    return false; 
}

### O(N²):
- O(N²) represents an algorithm whose performance is directly proportional to the square of the size of the input data set.
bool ContainsDuplicates(IList<string> elements)
{
    for (var outer = 0; outer < elements.Count; outer++) 
    {
        for (var inner = 0; inner < elements.Count; inner++) 
        { 
            // Don't compare with self 
            if (outer == inner) continue;             
            
            if (elements[outer] == elements[inner]) return true; 
        }
    }    
    return false;
}

### O(2^N):
- O(2^N) denotes an algorithm whose growth doubles with each addition to the input data set. 
int Fibonacci(int number)
{
    if (number <= 1) return number;
       
    return Fibonacci(number - 2) + Fibonacci(number - 1); 
}

### Logarithms:
- Binary search is a technique used to search sorted data sets. It works by selecting the middle element of the data set, essentially the median, and compares it against a target value.
