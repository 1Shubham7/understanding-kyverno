## Understanding Chainsaw



class Person{
    String name;
    int age;
    
    public Person(String name, int age){
        this.name = name;
        this.age = age;
    }
    
    public static void main(String[] args){
        Person one = new Person("Shubham", 100);
        Person two = new Person("Shiv", 120);
        
        System.out.println("Name is "+ one.name);
        System.out.println("Name is "+ two.name);
    }
}
