# The Marco to create a java source file

* create a java source file under the project root using `vim {java source file}` command,
and execute the follow marco:

```
i^R%^[<80><fd>aF/<80><fd>aD^[o^[<80><fd>ao^[p0xf.<80><fd>aD^[ggdf/<80><fd>a:s@/@.@g^MIpackage ^[A;^[GIpublic class ^[A {^M}^[<80><fd>aO public static void main(String[] args) {^M}^[<80><fd>aO^[<80><fd>a
```
