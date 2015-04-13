# Datecalculator
package dayscalc;

import java.util.Scanner;

public class Dayscalculate {

	public static void main(String[] args) {
		// TODO 自动生成的方法存根
  System.out.println("请输入年份：");
		Scanner input =new Scanner(System.in);
  int year=input.nextInt();
  System.out.println("请输入月份： ");
  Scanner input2 =new Scanner(System.in);
  int month=input2.nextInt();
  System.out.println("请输入日期：");
  Scanner input3=new Scanner(System.in);
  int day=input3.nextInt();
  //计算距离Java 1.0发布 1995.5.23已经过了多少天；
  
  
  Dayscalculate world=new Dayscalculate();
  int result=world.calcuDays(year,month,day);
  System.out.println("距离java1.0发布已经过了"+result+"天");
  	}
  
  int calcuDays(int year,int month,int day){
  //对于1995年做单独的考虑
	  int sum=0;
  if(year==1995){
	  if(month==5)
		  sum=day-23;
	  else{
		  sum=sum+8;
	  for(int m=6;m<month;m++){
		  if(m==6||m==9||m==11)
			  sum=sum+30;
		  else
			  sum=sum+31;
	  }
	  sum=sum+day;
	  }	  
  }
  //如果年份大于1995时
  else{
	  sum=sum+223;
  for(int i=1996;i<year;i++){
	  //实现对每一年所过的月份的计算
	  for(int j=1;j<=12;j++){
		 switch(j){
		  case 1:
			  sum=sum+31;
			  break;
		   case 2:
			   if(i%4==0){
				   if(i%100==0&&i%400!=0)
					   sum=sum+28;
				   else
				    sum=sum+29;
				   }
			   else
				   sum=sum+28;
			   break;
		   case 3:
			   sum=sum+31;
			  break;
		   case 4:
			   sum=sum+30;
			   break;
		   case 5:
			   sum=sum+31;
			   break;
		   case 6:
			   sum=sum+30;
			   break;
		   case 7:
			   sum=sum+31;
			   break;
		   case 8:
			   sum=sum+31;
			   break;
		   case 9:
			   sum=sum+30;
			   break;
		   case 10:
			   sum=sum+31;
			   break;
		   case 11:
			   sum=sum+30;
			   break;
		   case 12: 
			   sum=sum+31;
			   break;
			     }
		   }
	  
	  }
      //再对当年进行单独考虑
     for(int n=1;n<month;n++){ 
    	 switch(n){
		  case 1:
			  sum=sum+31;
			  break;
		   case 2:
			   if(year%4==0){
				   if(year%100==0&&year%400!=0)
					   sum=sum+28;
				   else
				    sum=sum+29;
				   }
			   else
				   sum=sum+28;
			   break;
		   case 3:
			   sum=sum+31;
			  break;
		   case 4:
			   sum=sum+30;
			   break;
		   case 5:
			   sum=sum+31;
			   break;
		   case 6:
			   sum=sum+30;
			   break;
		   case 7:
			   sum=sum+31;
			   break;
		   case 8:
			   sum=sum+31;
			   break;
		   case 9:
			   sum=sum+30;
			   break;
		   case 10:
			   sum=sum+31;
			   break;
		   case 11:
			   sum=sum+30;
			   break;
		   case 12: 
			   sum=sum+31;
			   break;
			     } 
     }
     sum=sum+(day-1);
  }
  return sum;
  } 
	}

