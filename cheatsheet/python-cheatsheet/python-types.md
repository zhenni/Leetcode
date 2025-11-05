# Python Types

### String

{% embed url="https://docs.python.org/3/library/string.html" %}

```python
my_string = "Hello World!"
lowercase_string = my_string.lower()

text3 = "123456"
print(f"'{text3}' is alphanumeric: {text3.isalnum()}")  # True
invalid_text1 = "Python 123"  # Contains a space
print(f"'{invalid_text1}' is alphanumeric: {invalid_text1.isalnum()}") # False
```

```python
string.ascii_letters
The concatenation of the ascii_lowercase and ascii_uppercase constants described below. This value is not locale-dependent.

string.ascii_lowercase
The lowercase letters 'abcdefghijklmnopqrstuvwxyz'. This value is not locale-dependent and will not change.

string.ascii_uppercase
The uppercase letters 'ABCDEFGHIJKLMNOPQRSTUVWXYZ'. This value is not locale-dependent and will not change.

string.digits
The string '0123456789'.

string.hexdigits
The string '0123456789abcdefABCDEF'.

string.octdigits
The string '01234567'.

string.punctuation
String of ASCII characters which are considered punctuation characters in the C locale: !"#$%&'()*+,-./:;<=>?@[\]^_`{|}~.

string.printable
String of ASCII characters which are considered printable by Python. This is a combination of digits, ascii_letters, punctuation, and whitespace.

Note By design, string.printable.isprintable() returns False. In particular, string.printable is not printable in the POSIX sense (see LC_CTYPE).
string.whitespace
A string containing all ASCII characters that are considered whitespace. This includes the characters space, tab, linefeed, return, formfeed, and vertical tab.
```

#### Format String

```python
"First, thou shalt count to {0}"  # References first positional argument
"Bring me a {}"                   # Implicitly references the first positional argument
"From {} to {}"                   # Same as "From {0} to {1}"
"My quest is {name}"              # References keyword argument 'name'
"Weight in tons {0.weight}"       # 'weight' attribute of first positional arg
"Units destroyed: {players[0]}"   # First element of keyword argument 'players'.
```

Aligning the text and specifying a width:

```python
'{:<30}'.format('left aligned')
'left aligned                  '
'{:>30}'.format('right aligned')
'                 right aligned'
'{:^30}'.format('centered')
'           centered           '
'{:*^30}'.format('centered')  # use '*' as a fill char
'***********centered***********'
```

Replacing `%+f`, `%-f`, and `% f` and specifying a sign:

```python
'{:+f}; {:+f}'.format(3.14, -3.14)  # show it always
'+3.140000; -3.140000'
'{: f}; {: f}'.format(3.14, -3.14)  # show a space for positive numbers
' 3.140000; -3.140000'
'{:-f}; {:-f}'.format(3.14, -3.14)  # show only the minus -- same as '{:f}; {:f}'
'3.140000; -3.140000'
```

Float

```python
value = 3.14159265 # Format to two decimal places
formatted_value = f"The value is: {value:.2f}"

signed_value = -12.345 # Format with a sign and two decimal places
formatted_signed = f"Signed value: {signed_value:+.2f}"

percentage_value = 0.75 # Format as a percentage
formatted_percentage = f"Percentage: {percentage_value:.2%}"

large_number = 1234567.89 # Format with thousands separator
formatted_large = f"Large number: {large_number:,.2f}"
```

Replacing `%x` and `%o` and converting the value to different bases:

```python
# format also supports binary numbers
"int: {0:d};  hex: {0:x};  oct: {0:o};  bin: {0:b}".format(42)
'int: 42;  hex: 2a;  oct: 52;  bin: 101010'
# with 0x, 0o, or 0b as prefix:
"int: {0:d};  hex: {0:#x};  oct: {0:#o};  bin: {0:#b}".format(42)
'int: 42;  hex: 0x2a;  oct: 0o52;  bin: 0b101010'
```

Using the comma or the underscore as a digit group separator:

```python
'{:,}'.format(1234567890)
'1,234,567,890'
'{:_}'.format(1234567890)
'1_234_567_890'
'{:_b}'.format(1234567890)
'100_1001_1001_0110_0000_0010_1101_0010'
'{:_x}'.format(1234567890)
'4996_02d2'
```

Expressing a percentage:

```python
points = 19
total = 22
'Correct answers: {:.2%}'.format(points/total)
'Correct answers: 86.36%'
```

Using type-specific formatting:

```python
import datetime
d = datetime.datetime(2010, 7, 4, 12, 15, 58)
'{:%Y-%m-%d %H:%M:%S}'.format(d)
'2010-07-04 12:15:58'
```

### Collections

{% embed url="https://docs.python.org/3/library/collections.html#collections.Counter" %}

```python
c = Counter()                           # a new, empty counter
c = Counter('gallahad')                 # a new counter from an iterable
c = Counter({'red': 4, 'blue': 2})      # a new counter from a mapping
c = Counter(cats=4, dogs=8)             # a new counter from keyword args

c = Counter(a=4, b=2, c=0, d=-2)
sorted(c.elements())                    # ['a', 'a', 'a', 'a', 'b', 'b']

for x, freq in c.items():               # iterate

sorted_by_frequency = counts.most_common()
#[('apple', 3), ('banana', 2), ('orange', 1), ('grape', 1)]
```

***

