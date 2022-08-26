# Compiler-Engineering---Pseudocode-to-Java-Translator

Parser and translator for a language supporting string operations. The language supports concatenation (+) and "reverse" operators over strings, function definitions and calls, conditionals (if-else i.e, every "if" must be followed by an "else"), and the following logical expression:

is-prefix-of (string1 prefix string2): Whether string1 is a prefix of string2.
All values in the language are strings.

The precedence of the operator expressions is defined as: precedence(if) < precedence(concat) < precedence(reverse).

The parser, based on a context-free grammar, will translate the input language into Java. You will use JavaCUP for the generation of the parser combined either with a hand-written lexer or a generated-one (e.g., using JFlex, which is encouraged).

The output language is a subset of Java so it can be compiled using javac and executed using Java or online Java compilers like this, if you want to test your output.

Example #1

Input:

    name()  {
        "John"
    }

    surname() {
        "Doe"
    }

    fullname(first_name, sep, last_name) {
        first_name + sep + last_name
    }

    name()
    surname()
    fullname(name(), " ", surname())
    

Output (Java):

public class Main {
    public static void main(String[] args) {
        System.out.println(name());
        System.out.println(surname());
        System.out.println(fullname(name(), " ", surname()));
    }

    public static String name() {
        return "John";
    }

    public static String surname() {
        return "Doe";
    }

    public static String fullname(String first_name, String sep, String last_name) {
        return first_name + sep + last_name;
    }
}