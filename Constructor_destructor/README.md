# Constructor and Destructor

```
#include <iostream>

using namespace std;

class ImmutableString {
	char* const str;
	const size_t size;
public:
  // TO DO ....
};



int main() {
	ImmutableString strs[] = {
		ImmutableString("C"), ImmutableString(),
		ImmutableString("Java"), ImmutableString("CSharp")
	};
	const int arraySize = sizeof(strs) / sizeof(ImmutableString);

	// [2]: Java
	const ImmutableString target("Java");
	for (size_t i = 0; i < arraySize; i++) {
		const ImmutableString str(strs[i]);
		if (str.isEqual(target)) {
			cout << "[" << i << "]: "; str.print(); break;
		}
	}
	// C
	//
	// Java
	// CSharp
	for (const ImmutableString& str : strs) {
		str.print();
	}
	vector<ImmutableString> strVector{ strs, strs + arraySize };
	size_t totalLength{};
	std::for_each(strVector.cbegin(), strVector.cend(),
		[&totalLength](const ImmutableString& str) {
			totalLength += str.getLength();
		}
	);
	cout << totalLength << endl; // 11
}
```

## Constrain
1. Implement class ImmutableString so that the following program runs
2. Implement all the member functions necessary for ImmutableString
3. Do not make any changes to the given code. Just add member functions, not modifying the data members.

