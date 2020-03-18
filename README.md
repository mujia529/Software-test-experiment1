# Software-test-experiment1
软件测试实验1
Shopping.java
package cn.tju.zxs01;
import java.util.Scanner;
public class Shopping {
	public static void main(String[] args) {
	
		Scanner scanner = new Scanner(System.in);
		int   x = scanner.nextInt();
		
		test1(x);
	}
	
	public static String test1(int x){
        int sum = 0;
        int count = 0;
        int t = 1;
        int f = 0;
        int[] a = {1, 5, 10, 20, 50};

        for (int i = 0; i <= 1; i++) {
            for (int j = 0; j <= 1; j++) {
                for (int k = 0; k <= 1; k++) {
                    for (int l = 0; l <= 2; l++) {
                        for (int m = 0; m <= 3; m++) {
                            sum = i * a[4] + j * a[3] + k * a[2] + l * a[1] + m * a[0] ;
                            if (sum == x) {
                            	count++;
                            }
                          
                            }
                          
                        }
                    }
                }
            }
        if(count>=1) {
        	 count = 0;
        	 return"can";
        }else {
        	  count = 0;
        	  return"can not";
        }
        }











TestShopping.java
package cn.tju.zxs01;

import static org.junit.Assert.*;



import org.junit.Before;
import org.junit.Test;
import org.junit.runner.RunWith;
import org.junit.runners.Parameterized;
import org.junit.runners.Parameterized.Parameters;
import java.util.Collection;
import java.util.Arrays;
 



@RunWith(Parameterized.class)
public class TestShopping {
	private int input1;
	private String expected ;
	private Shopping s = null;
public TestShopping(int input1,String expected){
	this.input1 = input1;
	this.expected = expected;
}
@Before
public void setUp(){
	s = new Shopping();
}
@Parameters
public static Collection<Object[]> getResult(){
	return Arrays.asList(new Object[][]{
			{3,"can"},
			{7,"can"},
			{11,"can"},
			{17,"can"},
			{6,"can not"},
			{46,"can not"}
			});
}
@Test
public void testShopping() {
	
	assertEquals(this.expected,s.test1(input1));
} }
