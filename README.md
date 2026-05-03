import java.io.*;
import java.util.*;

public class Solution {
static boolean isPrime(int num) {
        if (num < 2) return false;
        if (num == 2) return true;
        if (num % 2 == 0) return false;

        for (int i = 3; i * i <= num; i += 2) {
            if (num % i == 0)
                return false;
        }
        return true;
    }
 public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int N = sc.nextInt();

        int smallerPrime = -1;
        int largerPrime = -1;
     for (int i = N - 1; i >= 2; i--) {
            if (isPrime(i)) {
                smallerPrime = i;
                break;
            }
        }
     for (int i = N + 1; ; i++) {
            if (isPrime(i)) {
                largerPrime = i;
                break;
            }
        }

        int gap = largerPrime - smallerPrime;

        if (gap % 2 == 0) {
            System.out.println("EVEN GAP");
        } else {
            System.out.println("ODD GAP");
        }
    }
}