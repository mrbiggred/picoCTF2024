Solved by luck.  I just happened to hit up and then delete on my keyboard by habbit and it caused a seg fault.

```
└─$ nc mimas.picoctf.net 53411
Welcome to our newly-opened burger place Pico 'n Patty! Can you help the picky customers find their favorite burger?
Here comes the first customer Patrick who wants a giant bite.
Please choose from the following burgers: Breakf@st_Burger, Gr%114d_Cheese, Bac0n_D3luxe
Enter your recommendation: ^[[A^[[A^[[A^[[A^[[A^[[A^[[A^[[A^[[A^[[A^[[A^[[A^[[B^[[B^[[B^[[B^[[B^[[B^[[B^[[B^[[B^[[B^[[B^[[B^[[B^[[B^[[B
There is no such burger yet!

picoCTF{7h3_cu570m3r_15_n3v3r_SEGFAULT_a1d85b3e}
```

The segfault prints the flag:

```python
void sigsegv_handler(int sig) {
    printf("\n%s\n", flag);
    fflush(stdout);
    exit(1);
}
```

Which is set in main:

```python
signal(SIGSEGV, sigsegv_handler);
```

The segfault happens because:

```python
#define BUFSIZE 32

char choice1[BUFSIZE];
scanf("%s", choice1);
```
