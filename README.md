import java.io.*;
public class Testnum {
    public static void main(String[] args) throws IOException {

        BufferedReader br1=new BufferedReader(new FileReader("F:\\Test\\numbers.txt"));
        PrintWriter pw=new PrintWriter("F:\\Test\\output.txt");
        String line1= br1.readLine();
        System.out.println("outside while");
        while(line1!=null)
        {
            BufferedReader br2=new BufferedReader(new FileReader("F:\\Test\\delete.txt"));
            String line2= br2.readLine();
            boolean flag=false;
            System.out.println("inside while");
            while(line2!=null)
            {
                System.out.println("inside while while");
                if(line1.equals(line2))
                {
                    System.out.println("inside while while if");
                    flag=true;
                    break;
                }
                line2= br2.readLine();
            }

            if(flag==false)
            {
                pw.println(line1);
                System.out.println("inside if");
            }
            line1=br1.readLine();
            br2.close();
        }
        pw.flush();
        br1.close();
        pw.close();
    }
}
