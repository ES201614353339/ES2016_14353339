#DeadLock

###ʵ�����
1.��дDeadlock.java

```java
class A{
    synchronized void methodA(B b){
    	b.last();
	}
	synchronized void last(){
		System.out.println("Inside A.last()");
	}
}
class B {
	synchronized void methodB(A a){
		a.last();
	}
	synchronized void last(){
		System.out.println("Inside B.last()");
	}
}
class Deadlock implements Runnable{
	A a = new A();
	B b = new B();
	
	Deadlock(){
		Thread t = new Thread(this);
		int count = 20000;
		
		t.start();
		while(count-->0);
		a.methodA(b);
	}
	
	public void run(){
		b.methodB(a);
	}
	public static void main(String args[]){
		new Deadlock();
	}
}
```
2.����
```
javac Deadlock.java
```
3.��дDeadlock.bat��������Deadlock.classͬһĿ¼��
```
cd /d %~dp0
@echo off
:start
set /a var+=1
echo %var%
java Deadlock
if %var% leq 1000 GOTO start
pause
```
4.������У����������������ϲ��������Ĵ���������ġ�
![deadlock.png](https://ooo.0o0.ooo/2016/11/11/58259cc95aca7.jpg)


###����ԭ�����
����������Ҫ�ĸ���Ҫ������<br /> 
1.����������һ����Դÿ��ֻ�ܱ�һ������ʹ�� <br /> 
2.�����뱣��������һ��������������Դ������ʱ�����ѻ�õ���Դ���ֲ���<br /> 
3.�����������������ѻ�õ���Դ����ĩʹ����֮ǰ������ǿ�а���<br /> 
4.ѭ���ȴ����������ɽ���֮���γ�һ��ͷβ��ӵ�ѭ���ȴ���Դ��ϵ<br /> 

���߳�t������ʱִ��run()������a��last(),��ʱ�����߳���ִ��a.methodA(b)ʱ,��Ҫִ��b.last(). A,B��Ϊʹ�ùؼ���synchronized���ε��࣬ͬһʱ��ֻ����һ���߳�ִ�����еĴ��룬���̺߳�t������Ϊû�еõ���Դ���������ȴ��Է�ִ�н���������������






