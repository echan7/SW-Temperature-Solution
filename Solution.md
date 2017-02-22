# SW-Temperature-Solution

class Solution {

    public static void main(String args[]) {
        Scanner in = new Scanner(System.in);
        int n = in.nextInt(); // the number of temperatures to analyse
        in.nextLine();
        String temps = in.nextLine(); // the n temperatures expressed as integers ranging from -273to 5526
        if(temps.equals("")){
            System.out.println("0");
        }else{    
            String[] tempers = temps.split(" ");
            int[] temperas = new int[tempers.length];
            for(int i =0; i < tempers.length; i++){
                temperas[i] = Integer.valueOf(tempers[i]);
            }
        
            int closest = Integer.MAX_VALUE;
            int index = 0;
            for(int i =0; i < temperas.length; i++){
                if(Math.abs(temperas[i]) < closest){
                    closest = Math.abs(temperas[i]);
                    index = i;
                }else if(Math.abs(temperas[i]) == closest){
                        if(temperas[index] >= 0){
                        }else if(temperas[index] < 0 && temperas[i] >= 0){
                            closest = temperas[i];
                            index = i;
                        }
                }   
            }    
            // Write an action using System.out.println()
            // To debug: System.err.println("Debug messages...");
    
            System.out.println(temperas[index]);
        }
    }
}
