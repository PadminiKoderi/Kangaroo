# Kangaroo
//https://www.hackerrank.com/challenges/kangaroo
//There are two kangaroos on an x-axis ready to jump in the positive direction (i.e, toward positive infinity). The first kangaroo //starts at location x1  and moves at a rate of v1 meters per jump. The second kangaroo starts at location x2 and moves at a rate of  //meters v2 per jump. Given the starting locations and movement rates for each kangaroo, can you determine if they'll ever land at the //same location at the same time?
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
class Solution {

    static void Main(String[] args) {
        string[] tokens_x1 = Console.ReadLine().Split(' ');
        int x1 = Convert.ToInt32(tokens_x1[0]);
        int v1 = Convert.ToInt32(tokens_x1[1]);
        int x2 = Convert.ToInt32(tokens_x1[2]);
        int v2 = Convert.ToInt32(tokens_x1[3]);
        int diff1,diff2,x1n,x2n;
        x1n=x1+v1;
        x2n=x2+v2;
        diff1=Math.Abs(x2n-x1n);
        if(diff1==0)
            Console.WriteLine("YES");
        else{
            while(true){
                x1n=x1n+v1;
                x2n=x2n+v2;
                diff2=Math.Abs(x2n-x1n);
                if(diff2==0){
                    Console.WriteLine("YES");
                    break;
                }
                else if(diff2>diff1){
                    Console.WriteLine("NO");
                    break;
                }
                else if(diff2==diff1){
                    Console.WriteLine("NO");
                    break;
                }
                else if(diff2<diff1){
                    diff1=diff2;
                }   
            }
        }
        
        
    }
}

