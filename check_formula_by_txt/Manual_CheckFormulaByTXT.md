# Format:
Copy the code from [here](https://github.com/Elteoremadebeethoven/MyAnimations/blob/master/check_formula_by_txt/check_formula_by_txt.py) and paste it in your code, and create an scene like this:
```python3
class CheckFormula(CheckFormulaByTXT):
    CONFIG={
      "text":TexMobject("...") # or TextMobject
    }
```
## Example:
```python3
class CheckFormula(CheckFormulaByTXT):
    CONFIG={
    "text":TexMobject(
        "\\sqrt{",
        "\\left(",
        "x",
        "+",
        "{",
        "b",
        "\\over",
        "2",
        "a",
        "}",
        "\\right)",
        "^",
        "2",
        "}",
        "=",
        "\\pm",
        "\\sqrt{",
        "{",
        "b",
        "^",
        "2",
        "-",
        "4",
        "a",
        "c",
        "\\over",
        "4",
        "a",
        "^",
        "{",
        ")",
        )
    }
```
The result is:

## Remove elements:
If you want to remove some elements you can use:
```python3
class CheckFormulaRemove(CheckFormulaByTXT):
    CONFIG={
    "text":TexMobject(
        "\\sqrt{","\\left(","x","+","{","b","\\over","2","a","}",
        "\\right)","^","2","}","=","\\pm","\\sqrt{","{","b","^",
        "2","-","4","a","c","\\over","4","a","^","{",")",
        ), # <- Add a comma
    "remove":[4,13,9,11,17,19,28,29] # <- Add here the list
    }
```
Result:

If you remove a element that appears in the formula, then this element shows in red:
```python3
class CheckFormulaBadRemove(CheckFormulaByTXT):
    CONFIG={
    "text":TexMobject(
        "\\sqrt{","\\left(","x","+","{","b","\\over","2","a","}",
        "\\right)","^","2","}","=","\\pm","\\sqrt{","{","b","^",
        "2","-","4","a","c","\\over","4","a","^","{",")",
        ),
    "remove":[4,13,9,11,19,17,28,29,7] # <- The element 7 missing
    }
```
Result:

## Highlight elements:
```python3
class CheckFormulaHightlight(CheckFormulaByTXT):
    CONFIG={
    "text":TexMobject(
        "\\sqrt{","\\left(","x","+","{","b","\\over","2","a","}",
        "\\right)","^","2","}","=","\\pm","\\sqrt{","{","b","^",
        "2","-","4","a","c","\\over","4","a","^","{",")",
        ),
    "remove":[4,13,9,11,17,19,28,29,7], # Add a comma
    "show_elements":[7,10,18] # <- Add the list
    }
```
Result:

## Change the direction and size of the numbers:
```python3
class CheckFormulaDirectionNumber(CheckFormulaByTXT):
    CONFIG={
    "text":TexMobject(
        "\\sqrt{","\\left(","x","+","{","b","\\over","2","a","}",
        "\\right)","^","2","}","=","\\pm","\\sqrt{","{","b","^",
        "2","-","4","a","c","\\over","4","a","^","{",")",
        ),
    "remove":[4,13,9,11,17,19,28,29,7],
    "show_elements":[7,10,18],
    "direction_numbers":DOWN,       # <- Direction
    "numbers_scale":0.9,            # <- Scale of the numbers
    "space_between_numbers":0.2     # <- Buff
    }
```
Result:

# If you want to export the number as a list in a .csv file check [this](link)