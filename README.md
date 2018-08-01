//برنامه ایی بنوسید که ماتریسی از ورودی گرفته بالا مثلثی بودن آن را بررسی نماید
# Session4-Ex11
package com.personal.Ex11;

import java.util.Scanner;

public class Ex11 {

	static Scanner sc;
	static int dimM,dimN;

	public static void main(String[] args) {
		
		
		System.out.println("Enter  the size of matrixes of 2d");
		System.out.println("Enter  the  dimention of matrixes");
		sc= new Scanner(System.in);
		dimM=sc.nextInt();
		dimN=dimM;
		int[][] arX= new int[dimM][dimN];
		
		System.out.println("Please enter the values of the  matrix:");
		System.out.println("*****************************");
		System.out.println("it should be: "+ dimM*dimN +"  Numbers");
		
		AddToMatrix(arX, dimM, dimN);
		printMatrix(arX, dimM, dimN);
		if (isUpperTriangularMatrix(arX, dimM, dimN)==1)
		System.out.println("The Matrix is Upper Triangular ");
		else
			System.out.println("The Matrix is not Upper Triangular ");

	}
	
    static int isUpperTriangularMatrix(int[][] arrX,int dimM, int dimN) {
    	
    	int counter=0;
    	int counterI=0;
    	for (int i = 0; i < dimM; i++) {
			counterI +=i;
			for (int j = 0; j < dimN; j++) {
				
				if(i==j && arrX[i][j] ==0) {
					break;
					
				}
				if(i>j && arrX[i][j]==0)
					counter++;
			
				
			}
			
		}
    	if(counter==counterI) {
			return 1;
					
    }
    	return -1;
    }
	
	 static void AddToMatrix(int[][] arr, int dimM, int dimN) {
	        for (int i = 0; i < dimM; i++) {
				
				for (int j = 0; j < dimN; j++) {
				
					arr[i][j]=sc.nextInt();
				}
				
			}
	        
			
	       	}
		static void printMatrix(int arr[][],int m, int n)
		{

		    for (int i=0; i<m; i++) {
		    	for (int j = 0; j < n; j++) {
		    		 System.out.print(String.format("%d\t", arr[i][j]));	
				}
		       
		    System.out.println();
		    }
		}


}
