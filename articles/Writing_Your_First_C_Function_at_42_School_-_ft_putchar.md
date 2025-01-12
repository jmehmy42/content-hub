# Writing Your First C Function at 42 School - ft_putchar

![](https://cdn-images-1.medium.com/max/1024/1*xornPYNZlnlcrdBb78vr8w.jpeg)

If you’re just diving into C programming, welcome to the wild ride! One of the first things you’ll tackle — especially if you’re at 42 and doing the **piscine** (hello, sleepless nights!) — is learning to write your own functions. And yes, you’ll quickly realize that C doesn’t come with all the handy tools you’re used to in modern programming languages. You want to print something? Forget about printf(). You’re on your own, buddy! 😅

But hey, don’t panic. Let’s start simple. We’re going to create a tiny but mighty function called ft\_putchar, and all it does is print a single character to your terminal. Think of it as your first baby step into the world of C functions. Trust me, you’ll thank yourself later when this becomes the building block for so many other cool things. Let’s break it down, one laugh at a time! 😄

### Understanding the ft\_putchar Function

Here’s the complete code:

```
#include <unistd.h>  
  
void ft_putchar(char c);  
  
void ft_putchar(char c)  
{  
    write(1, &c, 1);  
}
```

This program demonstrates how to define a custom function to output a character using the write system call. Let’s break it down in detail.

### 1. The #include Directive

```
#include <unistd.h>
```

The <unistd.h> library gives you access to the write function, which is used for low-level input/output operations in C. This header is essential for Unix-like operating systems (e.g., Linux, macOS).

* **Why use** **<unistd.h>?**
* It’s lightweight and focused on low-level operations.
* It directly interacts with system calls, making it suitable for custom libraries and embedded systems.

### 2. Declaring the Function

```
void ft_putchar(char c);
```

This is a function prototype, which informs the compiler about the function’s:

* **Name:** ft\_putchar
* **Return type:** void (indicates no return value)
* **Parameter type:** A single char input.

By declaring the function before main, the compiler knows its structure even before encountering its definition or use.

### 3. Defining the Function

```
void ft_putchar(char c)  
{  
    write(1, &c, 1);  
}
```

Here’s where the function is implemented. The write system call is the key component:

* **Syntax of****write:**

```
ssize_t write(int fd, const void *buf, size_t count);
```

* **fd (File Descriptor):** The number 1 represents standard output (stdout).
* **buf (Buffer):** The address of the character c to be written (&c).
* **count:** Specifies the number of bytes to write. For a single character, this is 1.

When executed, write sends the character c to the terminal.

### 4. The main Function

The main function included here is purely for testing purposes. In the 42 piscine, you'll need to comment out or remove the main function before submitting your code (trust me, it's a rule you don’t want to break). However, while you're learning and testing your functions, the main function is your best friend. It not only helps you ensure your function works as expected but also gives you a better understanding of how functions interact within your program. So, use it wisely during testing but remember to clean it up before turning in your work! 😉

```
int main()  
{  
    char a;  
    a = 'Z';  
    ft_putchar(a);  
}
```

The main function is the program's entry point. Here’s what happens step by step:

1. **Declare a Variable:**

```
char a;
```

1. A variable a is declared and initialized with the character 'Z'.

```
a = 'Z';
```

**Call** **ft\_putchar:**

```
ft_putchar(a);
```

1. The ft\_putchar function is called with a as its argument, printing 'Z' to the terminal.

### Output of the Program

When you compile and run the program:

```
$ gcc ft_putchar.c -o ft_putchar  
$ ./ft_putchar  
Z
```

You’ll see **Z** displayed in your terminal.

### Why Use ft\_putchar Instead of printf?

While the printf function can achieve the same result, ft\_putchar offers several advantages:

1. **Efficiency:**

* ft\_putchar is lightweight, as it avoids the overhead of the more complex <stdio.h> library.

**2. Low-Level Control:**

* Directly interacts with system calls, making it ideal for kernel programming, embedded systems, or building custom libraries.

**3. Educational Value:**

* It helps beginners grasp low-level I/O operations and understand how data is written to the terminal.

### Practical Enhancements

Once you’ve mastered ft\_putchar, consider building more advanced functions using it as a foundation:

1. **ft\_putstr:** A function to print strings by combining ft\_putchar with loops.
2. **ft\_putnbr:** A function to print numbers by converting integers to characters.
3. **Custom Libraries:** Add ft\_putchar to a library like [libft](https://github.com/) to create reusable tools for your projects.

### Conclusion

The ft\_putchar function may be simple, but it demonstrates critical concepts like function creation, parameter passing, and low-level system calls. Writing and understanding this function is a great stepping stone toward more complex programming tasks.

Challenge yourself by modifying this code to print different characters or even create new functions based on it. Small steps like this will lay the groundwork for becoming a proficient C programmer.

### Suggested Meta Description:

“Learn how to create the ft\_putchar function in C to print a single character. Understand the code step by step and explore its practical applications for low-level programming."

### Title Suggestions:

1. **“Building Blocks of C Programming: The** **ft\_putchar Function Explained"**
2. **“Master Low-Level I/O Operations in C: Writing the** **ft\_putchar Function"**
3. **“Learn to Write the** **ft\_putchar Function in C: A Beginner’s Guide"**
4. **“Simplify Character Output in C with the** **ft\_putchar Function"**

### Conclusion

The ft\_putchar function may seem simple, but it demonstrates many fundamental concepts in C, such as function creation, parameter passing, and system calls. By understanding and practicing this code, you'll build a strong foundation for more complex programming tasks.

Try modifying the code to print different characters, or expand it into a more comprehensive output library. Happy coding! 🚀

![](https://medium.com/_/stat?event=post.clientViewed&referrerSource=full_rss&postId=e5a74a55737f)

[Read on Medium](https://jaskaran42.medium.com/writing-your-first-c-function-at-42-school-ft-putchar-e5a74a55737f?source=rss-41f5a113b923------2)