# cs610-assignment-2-solved



**<span style='color:red'>TO GET THIS SOLUTION VISIT:</span>** https://www.ankitcodinghub.com/product/cs610-general-policies-solved-7/

<h2>Description</h2>



<div class="kk-star-ratings kksr-auto kksr-align-center kksr-valign-top" data-payload="{&quot;align&quot;:&quot;center&quot;,&quot;id&quot;:&quot;128532&quot;,&quot;slug&quot;:&quot;default&quot;,&quot;valign&quot;:&quot;top&quot;,&quot;ignore&quot;:&quot;&quot;,&quot;reference&quot;:&quot;auto&quot;,&quot;class&quot;:&quot;&quot;,&quot;count&quot;:&quot;1&quot;,&quot;legendonly&quot;:&quot;&quot;,&quot;readonly&quot;:&quot;&quot;,&quot;score&quot;:&quot;5&quot;,&quot;starsonly&quot;:&quot;&quot;,&quot;best&quot;:&quot;5&quot;,&quot;gap&quot;:&quot;4&quot;,&quot;greet&quot;:&quot;Rate this product&quot;,&quot;legend&quot;:&quot;5\/5 - (1 vote)&quot;,&quot;size&quot;:&quot;24&quot;,&quot;title&quot;:&quot;CS610 Assignment 2 Solved&quot;,&quot;width&quot;:&quot;138&quot;,&quot;_legend&quot;:&quot;{score}\/{best} - ({count} {votes})&quot;,&quot;font_factor&quot;:&quot;1.25&quot;}">
            
<div class="kksr-stars">
    
<div class="kksr-stars-inactive">
            <div class="kksr-star" data-star="1" style="padding-right: 4px">
            

<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="2" style="padding-right: 4px">
            

<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="3" style="padding-right: 4px">
            

<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="4" style="padding-right: 4px">
            

<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="5" style="padding-right: 4px">
            

<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>
    
<div class="kksr-stars-active" style="width: 138px;">
            <div class="kksr-star" style="padding-right: 4px">
            

<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">
            

<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">
            

<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">
            

<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">
            

<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>
</div>
                

<div class="kksr-legend" style="font-size: 19.2px;">
            5/5 - (1 vote)    </div>
    </div>
• You should do this assignment alone.

• Do not copy or turn in solutions from other sources. You will be penalized if caught.

Submission

• Submission will be through Canvas.

• Submit a compressed file called “⟨roll⟩-assign2.tar.gz”. The compressed file should have the following structure.

— roll

— — roll-assign2.pdf

— — &lt;problem1-dir&gt;

— — — &lt;source-files&gt; — — &lt;problem2-dir&gt;

— — — &lt;source-files&gt;

The PDF file should contain descriptions for the first two problems, and your solution for the last problem.

• We encourage you to use the LATEX typesetting system for generating the PDF file. You can use tools like Tikz, Inkscape, or Draw.io for drawing figures if required. You can alternatively upload a scanned copy of a handwritten solution, but make sure the submission is legible.

• You will get up to two late days to submit your assignment, with a 25% penalty for each day.

Evaluation

• Write your programs such that the exact output format (if any) is respected.

• We will evaluate your implementations on a Unix-like system, for example, recent Debianbased distributions installed on KD first floor labs.

• We will evaluate the implementations with our own inputs and test cases, so remember to test thoroughly.

You are given a multithreaded program with N threads. The program reads N files, and should report the total number of words and lines processed by all the threads.

We provide a driver source code for the problem. Your task is to analyze the source code, and identify and report the performance bugs present in the source code, if any. If a performance bug is identified, provide a manually fixed version. Describe your modifications to the source code and report the performance gain.

Use the following commands to compile the attached driver and run the sample test case.

make

./problem1.out 4 ./test1/input

You can use the perf c2c tool to identify some forms of performance bugs. You can use the following links to learn more about using perf.

• C2C – False Sharing Detection in Linux Perf

• perf c2c man page

Input The input to your program will be a path to a file, say input.

The file input lists the full paths of N source files that are to be processed by N threads. Read the contents of the file input into a shared data structure X. Each thread will then pick one file from the shared data structure to analyze. A thread reads its file one line at a time and divides the line into tokens. The thread updates a counter to track the words encountered by the threads and updates the shared variable to track the total number of places the line.

Example

File 1:

ABC, EFG HIJK.

LMNOP QRST.

File 2:

ABC EF HI LMNOPQ RST UV

Expected Output:

Thread 0 counter: 6

Thread 1 counter: 5

Total words processed: 11

Total lines processed: 4

Write a C++ program that takes five arguments from the command line: a string that represents the path to an input file to be read (say R), an integer representing the number of producer threads (say T), an integer representing the number of lines each thread should read from the file (say L), an integer representing the size of a shared buffer (say M), and a string that represents the path to an output file (say W).

Assume the file R to be read contains N lines. The program will launch the required number of threads T. After all the threads are created, the threads will contend for access to R to repeatedly read L consecutive lines. Then, each thread will write its share of L consecutive lines atomically to a FIFO shared buffer. A dedicated consumer thread (not included in T) keeps reading from the shared buffer and writes its contents to the destination file W.

• Blank lines are also counted.

• The input file can have more than T*L lines.

• The problem requires synchronization (barriers, mutexes, and condvars) at multiple places.

• All threads should acquire locks only for the minimum required duration (e.g., reader thread reading L lines).

• Use a conditional variable instead of busy waiting for synchronizing accesses to the shared buffer across producer and consumer threads.

• You are not allowed to use concurrent data structures, but you can use other STL data structures like std::vector and std::atomic.

• The application should terminate properly after all threads are done.

The goal of this problem is to achieve correctness. So, test your code thoroughly with different possible inputs.

Consider the following loop nest.

for i = 1, N-2

for j = i+1, N

A(i, j-i) = A(i, j-i-1) – A(i+1, j-i) + A(i-1, i+j-1)

1

2

3

List all flow, anti, and output dependences, if any, using the Delta test. Show your computation.

Assume all array subscript references of array A are valid.
