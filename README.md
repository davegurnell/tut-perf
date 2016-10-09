# Tut Performance Tests

This repo contains the results of timing `sbt tut` and `sbt tutQuick`
on projects of varying sizes.

`sbt tut` runs one Java process to compile all markdown files in the project,
whereas `sbt tutQuick` runs one process per individual file.

## Methodology

1. Create a project containing `n` identical markdown files;

2. repeatedly run the following script 
   (25 times, dump the results in the `logs` directory):

   ```
   sbt clean
   time sbt tut
   ```

3. record the mean of the resulting times 
   (add them to the Excel file in the `results` directory);

4. repeat 1 to 3 for the following script:

   ```
   sbt clean
   time sbt tutQuick
   ```

5. repeat the whole process for another value of `n`.

## Results

Running `sbt tut` is slightly faster for certain values of `n`,
but times quickly blow up for `n > ~40`.
The run time of `sbt tutQuick` scales linearly with project size:

![Results of running `sbt tut` and `sbt tutQuick`](https://github.com/davegurnell/tut-perf/blob/master/results/results.png)
