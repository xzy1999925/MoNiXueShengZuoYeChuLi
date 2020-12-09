# MoNiXueShengZuoYeChuLi
package shiyan;

import java.io.*;

public class Output extends Students{


    public static void main(String[] args) {
        Students stu = new Students();
        stu.name="邢朝阳";
        stu.id=2017310346;
        stu.sex="男";
        stu.age=21;
      
        try(FileReader reader = new FileReader("E:\\xuexi\\java-A.txt");
            FileWriter writer = new FileWriter("E:\\xuexi\\java-A.txt")
        ){
            StringBuffer sb = new StringBuffer();
            char[] cs = new char[14];
            while ((reader.read(cs)) != -1) {
                sb.append(cs , 0, 7);
                sb.append(", ");
                sb.append(cs, 7, 7);
                sb.append(". "+"\n");
            }
            System.out.println(sb);
            writer.write(stu.toString());
            writer.write("\n");
            writer.write(new String(sb));
            writer.flush();
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}

package shiyan;


public class Students {

    public String name;
    public int id;
    public String sex;
    public int age;

    public void Student(String name, int id, int age, String Sex){
        this.name = name;
        this.id = id;
        this.sex = Sex;
        this.age = age;
        
    }

    @Override
    public String toString() {
        return "Student: " +
                "name=" + name +  
                ", id=" + id +
                ", sex=" + sex  +
                ", age=" + age +
                
                ' ';
    }

    public String getName() {
        return name;
    }

    public int getId() {
        return id;
    }

    public String getGender() {
        return sex;
    }

    public int getAge() {
        return age;
    }

  
}
