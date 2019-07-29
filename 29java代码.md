``` bash
package 课后练习;

import java.util.Scanner;

public class Circle {
	private float radius;
	public Circle(float radius) {
		this.radius=radius;
	}
	public Circle() {
	}
public double getArea() {
	return Math.PI*radius*radius;
	
}
public double getPerimeter() {
	return Math.PI*radius*2;
}
public void show() {
	double area=getArea();
	double perimeter=getPerimeter();
	System.out.println("圆的半径"+radius+"周长为："+perimeter+"圆的面积"+area);
}
public static void main(String[] args) {
	Scanner sc=new Scanner(System.in);
	System.out.println("请输入圆的半径：");
	float r=sc.nextFloat();
	Circle cir=new Circle(r);
	cir.show();
}
}
```