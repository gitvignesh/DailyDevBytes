Solution: https://leetcode.com/problems/valid-parentheses/submissions/1287662723

```kotlin
fun isValid(s: String): Boolean {
	val outMap = hashMapOf(
		')' to '(',
		']' to '[',
		'}' to '{'
	)
	val opened = arrayListOf<Char>()

	for (bracket in s) {
		if(outMap.contains(bracket)){
			if (opened.isEmpty()) {
				return false
			} else {
				if (outMap[bracket] != opened.last()){
					return false
				} else {
					opened.removeLast()
				}
			}  
		} else {
			opened.add(bracket)
		}
	}
	return opened.isEmpty()
}
```