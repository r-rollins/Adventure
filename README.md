# Adventure
import java.util.Scanner;

public class Adventure {
    public static void main(String[] args) {
        starter();

        Scanner userInput = new Scanner(System.in);
        int ans = userInput.nextInt();

        int a = one(ans);

        if(a == 1) {
            choice1();
        }
        else if(a == 2) {
            choice2();
        }
        else {
            choice3();
        }
    }






    public static void starter(){
        System.out.println("You wake up in the middle of the forest, no idea where you are. It is snowing.");
        System.out.println("You stand up.  Which direction do you head?"); //question
        System.out.println("1. North \n2. South \n3. East"); //choice 1, 2, 3
    }

    public static void choice1(){
        int b = oneA(); //river?
        choicesOneA(b);

    }

    public static void choice2(){
        Scanner userInput = new Scanner(System.in);

        int b = oneB(); //ladder?
        if (b == 1) { //investigate
            int c = twoB(); //treehouse?
            if(c == 1) { //climb
                int d;
            }
            else { //keep walking
                int d = oneA();
                choicesOneA(d);
            }
        }
        else if(b == 2) { //turn around
            starter();
            int ans2 = userInput.nextInt();
            int c = one(ans2);
            if(c == 1) {
                choice1();
            }
            else if(c == 2) {
                choice2();
            }
            else {
                choice3();
            }
        }
        else { //continue south
            int c = oneA();
            choicesOneA(c);
        }
    }

    public static void choice3(){
        Scanner userInput = new Scanner(System.in);

        int b = oneC(); //bear?
        if (b == 1){ //play dead
            int c = twoC(); //direction?
            if(c == 1){ //north
                choice1();
            }
            else if(c == 2) { //east
                int d = threeC(); //cabin?
                if(d == 1) { //turn around
                    int e = twoC(); //direction?
                    if(e == 1) { //north
                        choice1();
                    }
                    else if(e == 2) { //east
                        int ans3 = userInput.nextInt();
                        int f = one(ans3); //beginning direction?
                        if(f == 1) { //north
                            choice1();
                        }
                        else if(f == 2) { //south
                            choice2();
                        }
                        else {
                            choice3(); //east
                        }
                    }
                    else { //west

                    }
                }
                else if(d == 2) { //knock

                }
                else { //windows

                }
            }
            else { //west
                int ans3 = userInput.nextInt();
                int d = one(ans3); //beginning direction?
                if(d == 1) { //north
                    choice1();
                }
                else if(d == 2) { //south
                    choice2();
                }
                else {
                    choice3(); //east
                }
            }
        }
        else { //attack
            int c = fourC();


        }
    }


    public static void choicesOneA(int b) {
        if(b == 2) { //right
            int c = twoA(); //walk on river?
            if(c == 1) { //keep walking
                int d = threeA(); //can't walk more?
                if(d == 1) { //sit by river
                    int e;
                }
                else{ //go towards trees
                    int e;
                }
            }
            else if(c == 2) { //stop
                int d = threeB(); //shelter?
                if(d == 1) { //trees
                    int e;
                } else { //boulders
                    int e;
                }
            }
            else { //turn around
                int d = oneA();
                choicesOneA(d);
            }
        }
        else { //left
            int c = oneB();
            if (c == 1) {
                int d = twoB();
                if(d == 1) { //climb
                    int e;
                }
                else if(d == 2) { //keep walking
                    int e;
                }
                else{
                    int e;
                }
            }
            else if(c == 2) {
                int d = oneA();
                choicesOneA(d);
            }
            else {

            }
        }
    }






    public static int one(int ans) {
        int a;

        if (ans == 1) {
            //choice 1
            System.out.println("You head North");
            a = 1;
        } else if (ans == 2) {
            //choice 2
            System.out.println("You head South");
            a = 2;
        } else {
            //choice 3
            System.out.println("You head East");
            a = 3;
        }
        return a;
    }

    public static int oneA() {
        System.out.println("You stumble upon a river. Do you...");
        System.out.println("1. Swim across \n2. Go to the right \n3. Go left");

        Scanner userInput = new Scanner(System.in);
        int ans = userInput.nextInt();

        int a = 0;
        if (ans == 1) {
            //choice 1
            System.out.println("You attempt to swim across." +
                    "\nThe river's current is too strong, and the water too cold." +
                    "\nYou do not make it.");
            gameOver();
        } else if (ans == 2) {
            //choice 2
            System.out.println("You walk to the right.");
            a = 2;
        } else {
            //choice 3
            System.out.println("You walk to the left.");
            a = 3;
        }
        return a;
    }

    public static int oneB() {
        System.out.println("You stumble upon a ladder, propped against a tree. Do you...");
        System.out.println("1. Investigate \n2. Turn around and go back \n3. Continue South");

        Scanner userInput = new Scanner(System.in);
        int ans = userInput.nextInt();

        int a;
        if (ans == 1) {
            //choice 1
            System.out.println("You walk to the ladder and look around.");
            a = 1;
        } else if (ans == 2) {
            //choice 2
            System.out.println("You turn around.");
            a = 2;
        } else {
            //choice 3
            System.out.println("You continue south.");
            a = 3;
        }
        return a;
    }

    public static int oneC() {
        System.out.println("After hours of walking, you encounter a black bear. Do you...");
        System.out.println("1. Play dead  \n2. Turn and run  \n3. Attack the bear ");

        Scanner userInput = new Scanner(System.in);
        int ans = userInput.nextInt();

        int a = 0;
        if (ans == 1) {
            //choice 1
            System.out.println("The bear doesn't notice you laying on the ground, and eventually leaves.");
            a = 1;
        } else if (ans == 2) {
            //choice 2
            System.out.println("Bears are much faster than humans.");
            gameOver();
        } else {
            //choice 3
            System.out.println("You run at the bear like a crazy person. The bear roars.");
            a = 3;
        }
        return a;
    }

    public static int fourC () {
        System.out.println("                           _,-'^\\\n" +
                "                       _,-'   ,\\ )\n" +
                "                   ,,-'     ,'  d'\n" +
                "    ,,,           J_ \\    ,'\n" +
                "   `\\ /     __ ,-'  \\ \\ ,'\n" +
                "   / /  _,-'  '      \\ \\\n" +
                "  / |,-'             /  }\n" +
                " (                 ,'  /\n" +
                "  '-,________         /\n" +
                "             \\       /\n" +
                "              |      |\n" +
                "             /       |\n" +
                "            /        |\n" +
                "           /  /~\\   (\\/)\n" +
                "          {  /   \\     }\n" +
                "          | |     |   =|\n" +
                "          / |      ~\\  |\n" +
                "          J \\,       (_o\n" +
                "           '\"");
        System.out.println("The bear runs at you. What do you do?");
        System.out.println("1. Turn and run! \n2. Grab a branch to fight with \nGo for the eyes");

        Scanner userInput = new Scanner(System.in);
        int ans = userInput.nextInt();

        int a = 0;
        if(a == 1) {
            gameOver();
        } else if(a == 2) {
            System.out.println("You grab a branch off the ground. " +
                    "You attempt to smack the bear but it breaks upon impact.");
            System.out.println("Do you...");
            System.out.println("1. Punch the bear's nose \n2. There's still time to run!");

            int ans2 = userInput.nextInt();

            if(ans2 == 1) {
                System.out.println("");
            } else {
                gameOver();
            }


        } else {
            System.out.println("The bear is stunned and blind now. Do you...");
            System.out.println("1. Punch its nose \n2. Make tons of noise \n3. Slap it");

        }



    }

    public static int twoA() {
        System.out.println("You walk along the river for a while, it's getting dark. Do you...");
        System.out.println("1. Keep walking \n2. Search for a place to stop \n3. Turn around");

        Scanner userInput = new Scanner(System.in);
        int ans = userInput.nextInt();

        int a;
        if (ans == 1) {
            //choice 1
            System.out.println("Your legs get tired quickly, you're getting colder but there is no shelter.");
            a = 1;
        } else if (ans == 2) {
            //choice 2
            System.out.println("You search quickly, scanning the tree line.");
            a = 2;
        } else {
            //choice 3
            System.out.println("You turn around, heading back where you came from.");
            a = 3;
        }
        return a;
    }

    public static int threeA() {
        System.out.println("You are exhausted and thirsty, unable to walk  further. Do you...");
        System.out.println("1. Sit down by the river, it's safer near the water \n2. Go towards the trees \n3. Drink some river water and continue walking");

        Scanner userInput = new Scanner(System.in);
        int ans = userInput.nextInt();

        int a = 0;
        if (ans == 1) {
            //choice 1
            System.out.println("You sit down near the edge of the river, resting.");
            a = 1;
        } else if (ans == 2) {
            //choice 2
            System.out.println("You find a spot between the trees, settling down and falling asleep.");
            a = 2;
        } else {
            //choice 3
            System.out.println("Less than ten minutes later, you collapse. Without food, water, and rest, you cannot continue...");
            gameOver();
        }
        return a;
    }

    public static int threeB() {
        System.out.println("You spot two possible places, one between two trees and another between two boulders by the shore of the river. Do you...");
        System.out.println("1. Choose the trees  \n2. Choose the boulders");

        Scanner userInput = new Scanner(System.in);
        int ans = userInput.nextInt();

        int a;
        if (ans == 1) {
            //choice 1
            System.out.println("You settle yourself between the trees after brushing aside some leaves. You fall asleep quickly.");
            a = 1;
        } else {
            //choice 2
            System.out.println("You settle yourself between the boulders, finding it hard to get comfy. You fall asleep quickly.");
            a = 2;
        }
        return a;
    }

    public static int twoB() {
        System.out.println("There is a treehouse at the top of the ladder. Do you...");
        System.out.println("1. Climb in! \n2. Keep on walking");

        Scanner userInput = new Scanner(System.in);
        int ans = userInput.nextInt();

        int a;
        if (ans == 1) {
            //choice 1
            System.out.println("You start to climb the ladder.");
            a = 1;
        }
        else {
            //choice 2
            System.out.println("This is sketchy. You walk past.");
            a = 2;
        }
        return a;
    }


    public static int twoC() {
        System.out.println("You stand. which direction do you head?");
        System.out.println("1. North \n2. East \n3. West ");

        Scanner userInput = new Scanner(System.in);
        int ans = userInput.nextInt();

        int a = 0;
        if (ans == 1) {
            //choice 1
            System.out.println("You head North.");
            a = 1;
        } else if (ans == 2) {
            //choice 2
            System.out.println("You head East.");
            a = 2;
        } else {
            //choice 3
            System.out.println("You turn around and head West.");
            a = 3;
        }
        return a;
    }

    public static int threeC() {
        System.out.println("You find a cabin in the woods. It looks unused, but you can't be sure. Do you...");
        System.out.println("1. Turn around, it could be occupied \n2. Go knock on the door, you could get help" +
                " \n3. Look through the windows");

        Scanner userInput = new Scanner(System.in);
        int ans = userInput.nextInt();

        int a = 0;
        if (ans == 1) {
            //choice 1
            System.out.println("You turn around and walk away.");
            a = 1;
        } else if (ans == 2) {
            //choice 2
            System.out.println("You walk to the door, knocking hesitantly. There is no reply.");
            a = 2;
        } else {
            //choice 3
            System.out.println("You peek through the window, noticing many \"trophies\" on the wall.");
            a = 3;
        }
        return a;
    }




    public static int template() {
        System.out.println(". Do you...");
        System.out.println("1.  \n2.  \n3. ");

        Scanner userInput = new Scanner(System.in);
        int ans = userInput.nextInt();

        int a = 0;
        if (ans == 1) {
            //choice 1
            System.out.println("");
            a = 1;
        } else if (ans == 2) {
            //choice 2
            System.out.println("");
            a = 2;
        } else {
            //choice 3
            System.out.println("");
            a = 3;
        }
        return a;
    }


























    public static void gameOver() {
        System.out.println("                 uuuuuuu\n" +
                "             uu$$$$$$$$$$$uu\n" +
                "          uu$$$$$$$$$$$$$$$$$uu\n" +
                "         u$$$$$$$$$$$$$$$$$$$$$u\n" +
                "        u$$$$$$$$$$$$$$$$$$$$$$$u\n" +
                "       u$$$$$$$$$$$$$$$$$$$$$$$$$u\n" +
                "       u$$$$$$$$$$$$$$$$$$$$$$$$$u\n" +
                "       u$$$$$$\"   \"$$$\"   \"$$$$$$u\n" +
                "       \"$$$$\"      u$u       $$$$\"\n" +
                "        $$$u       u$u       u$$$\n" +
                "        $$$u      u$$$u      u$$$\n" +
                "         \"$$$$uu$$$   $$$uu$$$$\"\n" +
                "          \"$$$$$$$\"   \"$$$$$$$\"\n" +
                "            u$$$$$$$u$$$$$$$u\n" +
                "             u$\"$\"$\"$\"$\"$\"$u\n" +
                "  uuu        $$u$ $ $ $ $u$$       uuu\n" +
                " u$$$$        $$$$$u$u$u$$$       u$$$$\n" +
                "  $$$$$uu      \"$$$$$$$$$\"     uu$$$$$$\n" +
                "u$$$$$$$$$$$uu    \"\"\"\"\"    uuuu$$$$$$$$$$\n" +
                "$$$$\"\"\"$$$$$$$$$$uuu   uu$$$$$$$$$\"\"\"$$$\"\n" +
                " \"\"\"      \"\"$$$$$$$$$$$uu \"\"$\"\"\"\n" +
                "           uuuu \"\"$$$$$$$$$$uuu\n" +
                "  u$$$uuu$$$$$$$$$uu \"\"$$$$$$$$$$$uuu$$$\n" +
                "  $$$$$$$$$$\"\"\"\"           \"\"$$$$$$$$$$$\"\n" +
                "   \"$$$$$\"                      \"\"$$$$\"\"\n" +
                "     $$$\"                         $$$$\"\n");
    }
}
