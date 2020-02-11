# CSS Tricks

## Box-shadow

box-shadow: horizontal   vertical  blur  spread  color

Can also be inset with the word inset

Order:
Bottom   top  Right  Left
Example (left and right box-shadows only)
``` css
box-shadow: 0 9px 0px 0px white, 0 -9px 0px 0px white, 12px 0 28px -15px #ddd, -12px 0 28px -15px #ddd;
```

## Attribute Selectors[att^=val]

Represents an element with the att attribute whose value begins with the prefix “val”. If “val” is the empty string then the selector does not represent anything. 
[att$=val] 
Represents an element with the att attribute whose value ends with the suffix “val”. If “val” is the empty string then the selector does not represent anything. 
[att*=val] 
Represents an element with the att attribute whose value contains at least one instance of the substring “val”. If “val” is the empty string then the selector does not represent anything. 