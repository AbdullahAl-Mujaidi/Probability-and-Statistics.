# Probability-and-Statistics.
برنامج بسيط بلغة الجافا يقوم بحسابة الوسط والوسيط والمنوال للبيانات الغير مبوبة
import java.util.Scanner;
class aa{ 
 int x[];
public aa(int size){
    x=new int[size];
} 
 public int mean(){
   int sum=0;
     for(int i=0;i<x.length;i++)   
     sum+=x[i];
     return sum/x.length;
 } 
public void order(){
    int temp=0;
    for(int i=0;i<x.length;i++) 
    for(int j=i+1;j<x.length;j++)
    if(x[i]<x[j]){
      temp=x[i];
        x[i]=x[j];
        x[j]=temp;
    }
}
    public double median(){
        order();
        int length=0;
        double median=0.0;
        if(x.length%2==0){
            length=((x.length/2));
            median=((double)(x[length]+x[length-1])/2);
            
            return median;
            
            
        }
       if(x.length%2!=0){
           length=((x.length+1)/2)-1;return x[length];}
        
        
        return 0;
        
    }
    public int mod(){
        int index=0;
       int max=0,max1=0;
        for(int i=0;i<x.length;i++){
        for(int j=i+1;j<x.length;j++)
        if(x[i]==x[j]) max1++; 
            if(max1>max){max=max1;index=i;}
            max1=0;
        }
        
        return x[index];
    }
    public double Q1(){
        int length=0;
        length=((x.length+1)/2)-1;
        return (double)x[length]+x[length-1]/2;
    }
}
public class Main {
    
    public static void main(String[] args) {
        Scanner a=new Scanner(System.in);
        System.out.print("ادخل عدد العناصر");
        int x=a.nextInt();
        aa b=new aa(x);
        for(int i=0;i<x;i++)
        b.x[i]=a.nextInt();
        
        System.out.println( "mode is"+b.mean() );
        System.out.print( "medin is"+b.median());
       System.out.print( "medin is"+b.mod());
    }
    
}
