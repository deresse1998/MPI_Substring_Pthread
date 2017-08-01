# MPI Substring using Pthread

Given two character strings s1 and s2. Using C and pthread to write a parallel program to
find out the number of substrings, in string s1, that are exactly the same as string s2. The
strings are ended with ‘\0’. For example, suppose number_substring(s1, s2) implements
the function, then number_substring(“abcdab”, “ab”) = 2, number_substring(“aaa”, “a”)
= 3, number_substring(“abac”, “bc”) = 0. Suppose the size of s1 and s2 are n1 and n2,
respectively, and p threads are used, we assume that n1 mod p = 0, and n2 < n1/p.
Strings s1 and s2 are stored in a file named “strings.txt”. String s1 is evenly partitioned
among p threads to concurrently search for matching with string s2. After a thread
finishes its work and obtains the number of local matchings, this local number is added
into a global variable showing the total number of matched substrings in string s1. Finally
this total number is printed out. The format of the strings.txt is like this (the first string is
s1 and the second one is s2):

       abcassghbca
       bca

In the program, use #define to specify number of threads to be created. For example:

	#define NUM_THREADS 5
