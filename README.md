# basis
Describes common statements in Java learning
//随机数的产生

//1
Random random=new Random();
int number=random.nextInt(max)%(max-min+1)+min;
//产生min~max的随机数

//2
int numberrandom.nextInt(n)
//产生0~n的随机数

//3
int random1=(int)(Math.random()*100+1);
//Math.random()的范围为0~1，故乘以100加一的随机数为0~100

