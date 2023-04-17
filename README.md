import java.util.Arrays;
import java.util.Scanner;

// Kenyah Collins, 2/13/2023, The purpose of this program is to help a user create a grocery list without duplicate items using arrays and loops
public class Main {
    private static Scanner input = new Scanner(System.in);

   //method to figure out if grocery item a user inputted is a duplicate
    public static boolean isDuplicate(String item, String[] list, int listcnt) {

        boolean result = false;
        for (int i=0; i<listcnt;++i) {
            if (item.equalsIgnoreCase(list[i])) {
                result = true;
            }
        }
        return result;
    }

    public static void main(String[] args) {

        //title
        System.out.println("\tGrocery Store List");
        System.out.println();

        int count = 0; // Number of items currently in the grocery list
        String[] groceryList = new String[6]; //array of grocery items

        //user input + use of method isDuplicate
        while (count < groceryList.length) {
            System.out.print("Enter grocery item: ");

            String item = input.next();
            if (isDuplicate(item,groceryList,count)) {
                System.out.println("Sorry, item: " + item + " is a duplicate");
            } else {
                groceryList[count] = item;
                count++;
            }
        }
        //output users final sorted grocery list
        Arrays.sort(groceryList);
        System.out.println("\nYour Grocery List:");
        for (String item: groceryList){
        System.out.println(item);
        }
    }
}
