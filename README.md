# Valid-Perfect-Square-DAY-5-CHALLENGE
class Solution {
    public boolean isPerfectSquare(int num) {
        long i = 0;
        for (; i * i < num; i++);
        return num == i * i;
    }
}
