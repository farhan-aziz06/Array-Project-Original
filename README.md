            # Array-Project-Original
            Array Project-Original


            import java.util.Arrays;
            import java.util.Scanner;

            public class Main {
                public static void main(String[] args) {
                    Scanner console = new Scanner(System.in);
                    int counter = 1;
                    while (counter >=0){
                        int[] numbber = {1, 8, 3, 4, 2, 9, 5};
                        int []binaryArray={1,2,3,4,5,6,7,8};
                        String[] list = {"Farhan", "Hammad", "Arshaman", "Adnan"};
                        System.out.println("Enter 1 for 1-D Array and 2 for 2-D Array: ");
                        int Choice = console.nextInt();

                        if (Choice==2){
                            System.out.println("Enter 1 to Check Simple Integer type 2-Array," +
                                    " Or Enter 2 to Check Empty 2-Array of your Choice: ");
                            int Choice2d = console.nextInt();

                            if (Choice2d ==1){
                                Array2d();
                            }
                            if (Choice2d==2){
                                array2dFromUser();
                            }
                        } else if (Choice==1) {
                            System.out.println("Enter 1 to To Check Array method Simple: \n Enter 2 For Liner Search : " +
                                    "\n Enter 3 For Binary Search: \n Enter 4 For Selection Sorting : \n Enter 5 For Random Shuffling : " +
                                    "\n Enter 6 To Generate a Array with Random element: \n Enter 7 to find pairs of array elements: ");
                            int Choice1D = console.nextInt();
                            switch (Choice1D){
                                case 1:
                                    System.out.println("Enter 1 for Array method without return or 2 for Array method with return: ");
                                    int ArrayMethodChoice= console.nextInt();
                                    if (ArrayMethodChoice==1){
                                        arrayMethod(numbber);
                                    } else if (ArrayMethodChoice==2) {
                                        arrayMethodreturn(numbber);
                                    }
                                    break;
                                case 2:
                                    System.out.println("Linear Search: Element is on Index " + LinearSearch(numbber));
                                    break;
                                case 3:
                                    System.out.println("Binary Search: Element is on Index " + BinarySearch(binaryArray));
                                    System.out.println("Binary Search by In-Built Method: Element is on Index " + Arrays.binarySearch(binaryArray, 3));
                                    break;
                                case 4:
                                    SelectionSorting(numbber);
                                    break;
                                case 5:
                                    RandomShuffling();
                                    break;
                                case 6:
                                    RandomArray();
                                case 7:
                                        /*for(int i = 0; i<args.length; i++) {
                                            System.out.println("args[" + i + "]: " + args[i]);
                                        }

                                         */
                                    PairsInArray(numbber);

                            }
                        }
                        System.out.println("Enter negative number to exit or any other number to continue...");
                        counter = console.nextInt();
                    }
                            // Methods of Array...

                }

                        public static void RandomArray(){
                            int [] array = new int[10];
                            for (int i=0; i<array.length;i++){
                                System.out.print(" ");
                                System.out.print( array[i]=(int)(Math.random()*10));
                            }
                        }
                        public static void RandomShuffling(){
                            int [] array ={1,2,3,4,5};
                            for(int i= array.length-1 ; i>0 ; i--){
                                int j= (int)(Math.random()*(i+1));
                                int temp=array[i];
                                array [i]=array [j];
                                array[j]=temp;
                            }
                            System.out.println(" Array is  Randomly Shuffle as : ");
                            for (int i=0; i<array.length ; i++){
                                System.out.print(array[i]+",");
                            }

                        }

                        public static void SelectionSorting(int[] sort){
                            int minValue,minIndex, temp =0;
                            for (int i =0; i<sort.length;i++){
                                minValue=sort[i];
                                minIndex=i;
                                for (int j =0; j<sort.length;j++){
                                    if (minValue>sort[j]){
                                        minValue=sort[j];
                                        minIndex=j;
                                    }
                                }
                                if (minValue<sort[i]){
                                    temp = sort[i];
                                    sort[i]=sort[minIndex];
                                    sort[minIndex]=temp;

                                }
                            }
                           // return sort;
                        }

                        public static void arrayMethod(int[] array) {
                            System.out.println("Sum with out return or by using built-in method " +
                                    Arrays.stream(array).sum());
                        }

                        public static int arrayMethodreturn(int[] arrayreturn) {
                            int sum = 0;
                            for (int i = 0; i < arrayreturn.length; i++) {
                                sum += arrayreturn[i];
                            }
                            return sum;
                        }

                        public static int LinearSearch(int[] arrayForLinearSearch) {
                            int key = 4;
                            for (int i = 0; i < arrayForLinearSearch.length; i++) {
                                if (key == arrayForLinearSearch[i]) {
                                    return i;
                                }

                            }
                            return -1;

                        }

                        public static int BinarySearch(int[] arrayForBinarySearch) {
                            int key = 6;
                            int start = 0, end = arrayForBinarySearch.length - 1;

                            while (start <= end) {
                                int mid = (start + end) / 2;
                                if (arrayForBinarySearch[mid] == key) {
                                    return mid;
                                } else if (arrayForBinarySearch[mid] < key) {
                                    start = mid + 1;
                                } else if (arrayForBinarySearch[mid] > key) {
                                    end = mid - 1;
                                }
                            }
                            return -1 - end;
                        }

                        public static void PairsInArray(int[] ForPairsOfArray) {
                            for (int i = 0; i < ForPairsOfArray.length; i++) {
                                int current = ForPairsOfArray[i];
                                for (int j = i + 1; j < ForPairsOfArray.length; j++) {
                                    System.out.print("( " + current + "," + ForPairsOfArray[j] + ")");
                                }
                                System.out.println();
                            }

                        }


                        public static void Array2d() {
                            int[][] Arrays2D = new int[5][10];
                            for (int i = 0; i < Arrays2D.length; i++) {
                                for (int j = 0; j < Arrays2D.length; j++) {
                                    Arrays2D[i][j] = (int) (Math.random() * 10);
                                }

                            }
                            System.out.println();
                            for (int i = 0; i < Arrays2D.length; i++) {
                                for (int j = 0; j < Arrays2D[0].length; j++) {
                                    System.out.print(" " + Arrays2D[i][j]);
                                }
                                System.out.println();
                            }

                        }

                        public static void IntArray(){
                            Scanner sc = new Scanner(System.in);
                            System.out.print("Enter Rows i: ");
                            int row = sc.nextInt();
                            System.out.print("Enter Columns j: ");
                            int column = sc.nextInt();
                            System.out.println("Here is Your 2D Array of Type Int...");
                            int[][] ArrayInt = new int[row][column];
                            /*for (int i = 0; i < ArrayInt.length; i++) {
                                for (int j = 0; j < ArrayInt.length; j++) {
                                    ArrayInt[i][j] = (int) (Math.random() * 10);
                                }
                            }

                             */
                            System.out.println();
                            for (int i = 0; i < ArrayInt.length; i++) {
                                for (int j = 0; j < ArrayInt[0].length; j++) {
                                    System.out.print(" " + ArrayInt[i][j]);
                                }
                                System.out.println();
                            }

                        }
                        public static void DoubleArray(){
                            Scanner sc = new Scanner(System.in);
                            System.out.print("Enter Rows i: ");
                            int rowDouble = sc.nextInt();
                            System.out.print("Enter Columns j: ");
                            int columnDouble = sc.nextInt();
                            System.out.println("Here is Your 2D Array of Type Double...");
                            double[][] ArrayDouble = new double[rowDouble][columnDouble];
                            /*for (int i = 0; i < ArrayDouble.length; i++) {
                                for (int j = 0; j < ArrayDouble.length; j++) {
                                    ArrayDouble[i][j] = Math.round(Math.random());
                                }
                            }

                             */
                            System.out.println();
                            for (int i = 0; i < ArrayDouble.length; i++) {
                                for (int j = 0; j < ArrayDouble[0].length; j++) {
                                    System.out.print(" " + ArrayDouble[i][j]);
                                }
                                System.out.println();
                            }
                        }
                        public static void FloatArray(){
                            Scanner sc = new Scanner(System.in);

                            System.out.print("Enter Rows i: ");
                            int rowFloat = sc.nextInt();
                            System.out.print("Enter Columns j: ");
                            int columnFloat = sc.nextInt();
                            System.out.println("Here is Your 2D Array of Type Float...");
                            float[][] ArrayFloat = new float[rowFloat][columnFloat];
                            /*for (int i = 0; i < ArrayFloat.length; i++) {
                                for (int j = 0; j < ArrayFloat.length; j++) {
                                    ArrayFloat[i][j] = (Math.round((float) (Math.random() * 10)));
                                }
                            }

                             */
                            System.out.println();
                            for (int i = 0; i < ArrayFloat.length; i++) {
                                for (int j = 0; j < ArrayFloat[0].length; j++) {
                                    System.out.print(" " + ArrayFloat[i][j]);
                                }
                                System.out.println();
                            }
                        }
                        public static void StringArray(){
                            Scanner sc = new Scanner(System.in);
                            System.out.print("Enter Rows i: ");
                            int rowString = sc.nextInt();
                            System.out.print("Enter Columns j: ");
                            int columnString = sc.nextInt();
                            System.out.println("Here is Your 2D Array of Type String...");
                            String[][] ArrayString = new String[rowString][columnString];
                            System.out.println();
                            for (int i = 0; i < ArrayString.length; i++) {
                                for (int j = 0; j < ArrayString[0].length; j++) {
                                    System.out.print(" " + ArrayString[i][j]);
                                }
                                System.out.println();
                            }
                        }
                        public static void LongArray(){
                            Scanner sc = new Scanner(System.in);
                            System.out.print("Enter Rows i: ");
                            int rowLong = sc.nextInt();
                            System.out.print("Enter Columns j: ");
                            int columnLong = sc.nextInt();
                            System.out.println("Here is Your 2D Array of Type Long...");
                            long [][] ArrayLong = new long[rowLong][columnLong];
                            System.out.println();
                            /*for (int i = 0; i < ArrayLong.length; i++) {
                                for (int j = 0; j < ArrayLong.length; j++) {
                                    ArrayLong[i][j] = (Math.round((long) (Math.random()*5)));
                                }
                            }

                             */
                            for (int i = 0; i < ArrayLong.length; i++) {
                                for (int j = 0; j < ArrayLong[0].length; j++) {
                                    System.out.print(" " + ArrayLong[i][j]);
                                }
                                System.out.println();
                            }
                        }
                        public static void ShortArray(){
                            Scanner sc = new Scanner(System.in);
                            System.out.print("Enter Rows i: ");
                            int rowShort = sc.nextInt();
                            System.out.print("Enter Columns j: ");
                            int columnShort = sc.nextInt();
                            System.out.println("Here is Your 2D Array of Type Short...");
                            short [][] ArrayShort = new short[rowShort][columnShort];
                            System.out.println();
                            /*for (int i = 0; i < ArrayShort.length; i++) {
                                for (int j = 0; j < ArrayShort.length; j++) {
                                    ArrayShort[i][j] = (short) (Math.random()*1);
                                }
                            }

                             */

                            for (int i = 0; i < ArrayShort.length; i++) {
                                for (int j = 0; j < ArrayShort[0].length; j++) {
                                    System.out.print(" " + ArrayShort[i][j]);
                                }
                                System.out.println();
                            }
                        }
                        public static void CharArray(){
                            Scanner sc =new Scanner(System.in);
                            System.out.print("Enter Rows i: ");
                            int rowChar = sc.nextInt();
                            System.out.print("Enter Columns j: ");
                            int columnChar = sc.nextInt();
                            System.out.println("Here is Your 2D Array of Type Char...");
                            char [][] ArrayChar = new char[rowChar][columnChar];
                            System.out.println();
                            /*for (int i = 0; i < ArrayChar.length; i++) {
                                for (int j = 0; j < ArrayChar.length; j++) {
                                    ArrayChar[i][j] = (Math.round((char) (Math.random()*5)));
                                }
                            }

                             */
                            for (int i = 0; i < ArrayChar.length; i++) {
                                for (int j = 0; j < ArrayChar[0].length; j++) {
                                    System.out.print(" " + ArrayChar[i][j]);
                                }
                                System.out.println();
                            }
                        }
                        public static void ByteArray(){
                            Scanner sc = new Scanner(System.in);
                            System.out.print("Enter Rows i: ");
                            int rowbyte = sc.nextInt();
                            System.out.print("Enter Columns j: ");
                            int columnbyte = sc.nextInt();
                            System.out.println("Here is Your 2D Array of Type Byte...");
                            Byte [][] ArrayByte = new Byte[rowbyte][columnbyte];
                            System.out.println();
                            /*for (int i = 0; i < ArrayChar.length; i++) {
                                for (int j = 0; j < ArrayChar.length; j++) {
                                    ArrayChar[i][j] = (Math.round((char) (Math.random()*5)));
                                }
                            }

                             */
                            for (int i = 0; i < ArrayByte.length; i++) {
                                for (int j = 0; j < ArrayByte[0].length; j++) {
                                    System.out.print(" " + ArrayByte[i][j]);
                                }
                                System.out.println();
                            }
                        }
                        public static void BooleanArray(){
                            Scanner sc = new Scanner(System.in);
                            System.out.print("Enter Rows i: ");
                            int rowboolean = sc.nextInt();
                            System.out.print("Enter Columns j: ");
                            int columnboolean = sc.nextInt();
                            System.out.println("Here is Your 2D Array of Type Boolean...");
                            boolean [][] ArrayBoolean = new boolean[rowboolean][columnboolean];
                            System.out.println();
                            /*for (int i = 0; i < ArrayChar.length; i++) {
                                for (int j = 0; j < ArrayChar.length; j++) {
                                    ArrayChar[i][j] = (Math.round((char) (Math.random()*5)));
                                }
                            }

                             */
                            for (int i = 0; i < ArrayBoolean.length; i++) {
                                for (int j = 0; j < ArrayBoolean[0].length; j++) {
                                    System.out.print(" " + ArrayBoolean[i][j]);
                                }
                                System.out.println();
                            }
                        }

                        public static void array2dFromUser() {
                            Scanner sc = new Scanner(System.in);
                            System.out.printf("Select Data Type You Want to Enter: \n 1. For Int \n 2. For Double \n 3. For Float " +
                                    "\n 4. For String \n 5. For Long \n 6. For Short \n 7. For Char \n 8. For byte \n 9. For boolean:" );
                            System.out.println();
                            int SelectType = sc.nextInt();
                            switch (SelectType) {
                                case 1:
                                    IntArray();
                                    break;
                                case 2:
                                    DoubleArray();
                                    break;
                                case 3:
                                    FloatArray();
                                    break;

                                case 4:
                                    StringArray();
                                    break;

                                case 5:
                                    LongArray();
                                    break;

                                case 6:
                                    ShortArray();
                                    break;
                                case 7:
                                    CharArray();
                                    break;

                                case 8:
                                    ByteArray();
                                    break;
                                case 9:
                                    BooleanArray();
                                    break;
                                default:
                                    System.out.println("Wrong Input: ");


                            }
                        }
                    }
