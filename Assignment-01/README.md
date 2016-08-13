## Assignment 01

* Python 
    1. Program
        
        ```
            import sys
            x = 1
            # y = 0
            for i in range(int(sys.argv[1])):
                # y=y+x
                print x
        ```
        For finding Instruction count we have to run : perf stat python test.py 10
    
    2. Output
        
        ```
            1
            1
            1
            1
            1
            1
            1
            1
            1
            1

            Performance counter stats for 'python test.py 10':

            57.376978 task-clock (msec)         #    0.934 CPUs utilized          
                28 context-switches          #    0.488 K/sec                  
                 0 cpu-migrations            #    0.000 K/sec                  
             1,349 page-faults               #    0.024 M/sec                  
            2,84,32,456 cycles                    #    0.496 GHz                    
            <not supported> stalled-cycles-frontend 
            <not supported> stalled-cycles-backend  
            2,71,40,874 instructions              #    0.95  insns per cycle        
            60,41,526 branches                  #  105.295 M/sec                  
            2,47,433 branch-misses             #    4.10% of all branches        

           0.061438251 seconds time elapsed

        ```

* C++
    1. Program
        
        ```
            #include<iostream>
            using namespace std;
            #define loop 10
            int main(){
                int x=1;
                for(int i=0;i<loop;i++){
                    cout<<x<<endl;
                }
                return 0;
            }
        ```
        * Compile program by : g++ test.cpp and it will generate Executable a.out 
        * Now type : perf stat ./a.out
    
    2. Output

        ```
            1
            1
            1
            1
            1
            1
            1
            1
            1
            1

             Performance counter stats for './a.out':

              5.809792 task-clock (msec)         #    0.762 CPUs utilized          
                    21 context-switches          #    0.004 M/sec                  
                     0 cpu-migrations            #    0.000 K/sec                  
                   327 page-faults               #    0.056 M/sec                  
             27,91,985 cycles                    #    0.481 GHz                    
        <not supported> stalled-cycles-frontend 
        <not supported> stalled-cycles-backend  
         21,48,182 instructions              #    0.77  insns per cycle        
          3,87,628 branches                  #   66.720 M/sec                  
            10,721 branch-misses             #    2.77% of all branches        

            0.007623285 seconds time elapsed

        ```
