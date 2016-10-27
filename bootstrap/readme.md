The files in this repository are used to find the procedure that gives bootstrap support that measures shifts. 
The `bs_shift.RMD`file contains all the codes for bootstap procedure and analysis on comparing which method is the best on detecting shifts.

While trying to pursue my goal, professor Cecile and I have found out there are errors in the package `l1ou` that needs to be fixed. 

# Methodology

For this study, I used lizard data from "l1ou" R package and some analytic functions from "phylolm".   
These two R packages provide functions to study trait evolution from the data and help to detect   
evolutionary shifts faster and more precisely. I first estimated the shift configuration on a dataset  
based on one of 3 criteria: "AICc", "BIC" and "pBIC" (first criterion). Then, the model of this shift   
configuration was used to simulate bootstrap support values of shifts based on   
"AICc", "BIC" or "pBIC" (second criterion). There were nine combinations of the first and second criterion.  
I compared the bootstrap support values from these nine procedures and found out that AICc_pBIC was the most   
accurate procedure in a conservative way. AICc_pBIC can detect all the shifts with fewer false-positives;   
this happens when some edges which do not contain shift are detected as shift edges with high support.  

Reports
---------------------------------------
2016-10-08 Version 1.28 Regenerate the report based on the new version of `l1ou`
https://yuqing19118.github.io/bs_shift2016_08_24.html

2016-09-04 Version 1.28 Focus on the issue that there are more false-positives close the root. Tried setting the intercept as 0.
https://yuqing19118.github.io/bs_shift_noint2016_09_04.html

2016-09-02 Version 1.28 Checking if there are less false-positives if I change the optimal values for edges. Tried setting theta=theta/4.
https://yuqing19118.github.io/bs_shift_theta2016_09_02.html

2016-07-31 Version 1.24 The first bootstrap report.
https://github.com/yuqing19118/traitevoOUshift/blob/master/bootstrap/bs_shift.pdf

























Instructions to run long jobs on cluster
---------------------------------------

First: to `top` to check that the machine is available.
Do `less /proc/cpuinfo` to see how many processors the machine has.

Below: replace 'machine' by the name of a machine to use,
and replace 'sessionname' by the name of the session (make it up)

```
ssh machine
stashticket
tmux new-session -s session
```
now run this inside the tmux session:
```
ssh machine
R
[R commands]
```
then type `Control-a d` to "detach" the tmux session. It will continue to
run even if I logout. yeah!
Then check how things are running by loging back:

```
ssh machine
tmux list-sessions
tmux attach
```
check that everything is going well. If the job is finished,
exit the tmux session and log out from machine twice:
```
logout
exit
logout
```
If the job is not finished, detact the tmux session again
with `Control-a d`


Log on jobs that are running or finished running
------------------------------------------------

Do `ps` to get the job numbers or `ps -u sabrina`.
Do `date` to get exact date.

- on `emperor-02`: started job `jobID` on `date/time`, using
  commands in file `run_bootstrap.R`, with this:
  `myresultsL <- do.boot.sim(n_sim=100, nbootItr=100, seed=xxx, filename=xxx, numcores=xxx)`
  When it finished, time it took:
- on `othermachine`: 

