# gaming-breach

    import java.util.*;
    public class Main{
    public static void main(String[] args){
        Scanner scanner= new Scanner(System.in);
        String N=scanner.next();
        int K =scanner.nextInt();
        System.out.println(getBestRank(N,K));
        }
        private static String getBestRank(String N,int K){
            int length=N.length();
            if(K>=length)return "";

            StringBuilder bestRank=new StringBuilder();
            for(int i=0;i<length;i++){
                while(K>0 && bestRank.length()>0 && bestRank.charAt(bestRank.length()-1)>N.charAt(i)){
                    bestRank.deleteCharAt(bestRank.length()-1);
                    K--;
                }
                bestRank.append(N.charAt(i));
            }
            while(K>0){
                bestRank.deleteCharAt(bestRank.length()-1);
                K--;
            }
            return bestRank.toString();
        }
    }
