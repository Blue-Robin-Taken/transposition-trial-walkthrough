# Transposition Trial Walkthrough
Pico Link: https://play.picoctf.org/practice/challenge/312

## Solving
1. Notice that it rotates each group of three characters by a different amount
2. Adjust the string likewise (use a script or manually do it)

## The script that I used
```
bean = "heTfl g as iicpCTo{7F4NRP051N5_16_35P3X51N3_V9AAB1F8}7"  # Begin with the string
r = 2  # Set the rotate value
f_string = ""  # This is arbitrary, it's just a string to add to

def left_shift(string, n):  # Shift a string left by an amount
    return string[n:] + string[:n]

for i in range(int(len(bean)/3)):  # Loop for i in every three
    selected = bean[i*3:(i*3)+3]  # Select a string from the index and get three chars
    print(selected)
    f_string = f_string + left_shift(selected, r%3)  # Add to f_string the selected three chars rotated by a certain amount `r%3` ensures that the text doesn't go over index 
    print(left_shift(selected,r))
    r += 3  # shift rotate value
    print(r)
print(f_string)  # final value
```

## Flag
<details>
  <summary>Spoiler warning</summary>
picoCTF{7R4N5P051N6_15_3XP3N51V3_A9AFB178}
</details>
