import java.io.File;
import java.util.Arrays;
public class ViewallFile {

    //utility method to print a string
    static void print(String value) {
        System.out.println(value);
    }


    /**
     * Method to sort all files and folders in a directory
     *
     * @param dirName : directory name
     * @return : No return value. Sort and print out the result
     */
    private static void sortAll(String dirName) {
        File directory = new File(dirName);

        File[] filesArray = directory.listFiles();

        //sort all files
        Arrays.sort(filesArray);

        //print the sorted values
        for (File file : filesArray) {
            if (file.isFile()) {
                print("File : " + file.getName());
            } else if (file.isDirectory()) {
                print("Directory : " + file.getName());
            } else {
                print("Unknown : " + file.getName());
            }
        }
    }

    public static void main(String[] args) {
        sortAll("C://Programs/");
    }

}
------------------------------------------------------------
import java.io.File;
import java.io.IOException;

public class CreatenewFile {
   public static void main(String[] args) {
      try {
         File file = new File("E:\\AFSHA.txt");
         
         if(file.createNewFile())System.out.println("Success!");
         else System.out.println ("Error, file already exists.");
      }
      catch(IOException ioe) {
         ioe.printStackTrace();
      }
   }
}
-------------------------------------------------------
package P1;
import java.util.logging.Logger;
import java.io.FileWriter;
import java.io.IOException;

public class InsertmyRecord {

	public static void main(String[] args) {
		// TODO Auto-generated method stub
		String data = "MEHAR AFSHA, BANGALORE, INDIA";
			try {
				FileWriter output = new FileWriter("E:\\AFSHA.txt");
				output.write(data);
				System.out.println("data written successfuly");
				output.close();
			}
		catch (IOException e)
		{
			System.out.println("file write error");
		}

	}

}
-------------------------------------------------------
package P1;

import java.io.File;

public class SearchFile {
    
    public static void main(String[] argv) throws Exception
    {
        // Create an object of the File class
        // Replace the file path with path of the directory
        File directory = new File("E:\\");
  
        // store all names with same name
        // with/without extension
        String[] flist = directory.list();
        int flag = 0;
        if (flist == null) {
            System.out.println("Empty directory.");
        }
        else {
  
            // Linear search in the array
            for (int i = 0; i < flist.length; i++) {
                String filename = flist[i];
                if (filename.equalsIgnoreCase("AFSHA.txt")) {
                    System.out.println(filename + " found");
                    flag = 1;
                }
            }
        }
  
        if (flag == 0) {
            System.out.println("File Not Found");
        }
    }
}
---------------------------------------------------
import java.io.File;

public class DeleteFile { 
   public static void main(String[] args) { 
      try { 
         File file = new File("E:\\data.txt");
         if(file.delete()) { 
            System.out.println(file.getName() + " is deleted!");
         } else {
            System.out.println("Delete operation is failed.");
    		}
      } catch(Exception e) {
         e.printStackTrace();
      }
   }
}   
------------------------------------------------------------
