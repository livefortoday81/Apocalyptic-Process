/*# Apocalyptic-Process
A couple subroutines that will be useful in the end times.
Still in beta.  Final release coming soon!!!
*/

    package chapter4;
    import java.util.Scanner;

    public class Chapter4 {
    static Scanner scan = new Scanner (System.in);
    static int passwordCount;
    static String name;
    static boolean containsLetters;
    static String password;
    static String[] passwordKeeper = new String [3];
    static String passwordFriend;
    static int numberOfPeople;


    static void nameId(String name){
        name = name.toLowerCase();
        int i;
        for (i = 0; i < name.length(); i++){
            char ch = name.charAt(i);
                if (ch == 'a' || ch == 'e' || ch == 'i' || ch == 'o' || ch == 'u'){
                    System.out.print(ch + "-");
                }
                else {
                    System.out.print(ch);
                }
        }
        System.out.println();
        System.out.print("Your name is now going to change formats: \n");
        nameChange(name);
        
        
        
        
    }
    static void nameChange(String name){
        int i;
        for (i = 0; i < name.length(); i++){
            char ch = name.charAt(i);
                if (ch == 'a' || ch == 'e' || ch == 'i' || ch == 'o' || ch == 'u'){
                    System.out.print(ch + "=");
                }
                else {
                    System.out.print(ch);
                }
        }
        System.out.println();
        System.out.print("The format of your name has changed.\n");
        System.out.println("Your name: " + name);
    
    }
    static void badgeNumber (int N){
        System.out.print("System is checking whether\n" +
                         "or not your badge number contains\n" +
                         "any letters.\n");
        while (true){
        System.out.println("Reenter or enter your badge number " +
                        "or press a to exit: ");
        String numString = scan.next().toLowerCase();
        if (numString.equals("a")){
            System.out.print("You exited.\n");
            break;
        }
            try {
                int numStringRevised = Integer.parseInt(numString);
                    
                        System.out.println("Your badge number contains only digits.");
                        break;
                        
                    

            }
            catch (NumberFormatException e){
                System.out.print("Badge number must not contain any letters.\n");
                
                
            }
        }
        
    }
    
    static void doorAccess(String[] passwordKeeper){
        int i;
        for (i = 0; i < passwordKeeper.length; i++){
            System.out.println(passwordKeeper[i]);
        }
        
        
    }
    
    static void safetyLockout(int numPeople){
        
        
       
        String[] namesOfSecluded = new String [numPeople];
        namesOfSecluded = new String [numPeople];
        double[] weightOfSecluded;
        weightOfSecluded = new double [numPeople];
        int[] temperOfSecluded;
        temperOfSecluded = new int [numPeople];
        String[] occupationOfSecluded;
        occupationOfSecluded = new String [numPeople];
        
        while (namesOfSecluded.length > -1){
            System.out.println("Is " + numPeople + " the correct amount of \n" +
                "people on the floor?  Enter yes or enter no to exit. ");
                String response = scan.next().toLowerCase();
                if (response.equals("no")){
                break;
                }
            System.out.println("Enter a person's name or press a to exit: ");
            String secludedsName = scan.next();
                
            System.out.println("Enter their weight: ");
            double weight = scan.nextDouble();
            System.out.println("Enter their temperament on a " +
                    "scale of 1 - 10 (1 being nice, 10 being extremely mean.");
            int temper = scan.nextInt();
            System.out.println("Enter their occupation: ");
            String occupation = scan.next();
            System.out.println();
            namesOfSecluded[numPeople - 1] = secludedsName;
            weightOfSecluded[numPeople - 1] = weight;
            temperOfSecluded[numPeople - 1] = temper;
            occupationOfSecluded[numPeople - 1] = occupation;
            
            
            numPeople--;
            
        }
        
        int i;
        for (i = 0; i < numPeople - 1; i++){
            System.out.print((i + 1) + ".)  ");
            System.out.print("Name: " + namesOfSecluded[i] + ", ");
            System.out.print("Weight: " + weightOfSecluded[i] + ", ");
            System.out.print("Temprament: " + temperOfSecluded[i] + ", ");
            System.out.println("Occupation: " + occupationOfSecluded[i]);
        }
        
        
    }
    
    static void parser(String password){
        while (true){
            
            try {
                int passwordVerify = Integer.parseInt(password);
                System.out.println("Thank you " + name);
                break;
            }
            catch(NumberFormatException e){
                System.out.println("Your password contains letters.  Please reenter.");
               
            }
            break;
        }
    }
    
    
    
    public static void main(String[] args) {
        // TODO code application logic here
        
        System.out.print("Enter your name: \n");
        name = scan.next();
        nameId(name);
        
        
        int num = (int) (Math.random() * 100000);
             if (num < 50000){
                 System.out.print("Choose a badge number\n" +
                                  "It cannot contain any letters.  And\n" +
                                  "it must only be 5 max digits long.\n" +
                                  "Your badgenumber: " + num + "\n");
                 
                 
             
             
             }
        
        badgeNumber(num);
        
        
        System.out.println("What company do you work for? ");
        String whatCompany = scan.next();
        
        while (true){
        System.out.println("What is your password? ");
        password = scan.next();
        passwordCount = 0;
        while (passwordCount < 1){
        passwordKeeper[passwordCount] = password;
        passwordCount++;
                }
        parser(password);
        System.out.println(password);
            int i;
            for (i = 0; i < password.length(); i++){
                char ch = password.charAt(i);
                boolean letterTest = Character.isAlphabetic(ch);
                    if (letterTest == true){
                        System.out.println("Character " + (i + 1) + " is a letter. \n" +
                                "  Reenter password.");
                        containsLetters = true;
                        break;
                    }
                    else {
                        containsLetters = false;
                    }
                    
                    
                    
            }
            if (containsLetters == false){
                System.out.println("Your password is acceptable.");
                break;
            }
            
        }
        System.out.println("And now onto the next subroutine.");
        System.out.println("To begin, enter true");
        boolean init = scan.nextBoolean();
        
        int numPasswords = 1;
        while (numPasswords < 3){ 
        System.out.println("To initialize warheads, " + (3 - numPasswords) + " more password(s) must be " +
                
                "entered.  Only digits 0-9 are accepted.  Enter a password now: ");
        String passwordFriend = scan.next();
        parser(passwordFriend);
            int n; 
            for (n = 0; n < passwordFriend.length(); n++){
                char ch = passwordFriend.charAt(n);
                boolean isALetter = Character.isAlphabetic(ch);
                    if (isALetter == true){
                        numPasswords--;
                        break;
                    }
                    else {
                        passwordKeeper[numPasswords] = passwordFriend;
    
                    }
            }
        
        numPasswords++;
        }
        int i;
        for (i = 0; i < passwordKeeper.length; i++){
            System.out.print("Person " + (i + 1) + "'s password: " + passwordKeeper[i] + "\n");
        }
        doorAccess(passwordKeeper);
        
        System.out.println("And now, for the safety lockout subroutine...");
        System.out.println("How many people are on the floor? ");
        int numberOfPeople = scan.nextInt();
        safetyLockout(numberOfPeople);
        
    }
    
}
