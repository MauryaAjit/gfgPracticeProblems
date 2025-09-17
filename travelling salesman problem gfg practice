import java.util.ArrayList;
import java.util.Collections;
import java.util.List;

class Solution {

    public static int tsp(int[][] cost) {
        int numNodes = cost.length;
        List<Integer> nodes = new ArrayList<>();
        for (int i = 1; i < numNodes; i++) {
            nodes.add(i);
        }

        int minCost = Integer.MAX_VALUE;
        do {
            int currCost = 0;
            int currNode = 0;
            for (int i = 0; i < nodes.size(); i++) {
                currCost += cost[currNode][nodes.get(i)];
                currNode = nodes.get(i);
            }
            currCost += cost[currNode][0]; // return to start
            minCost = Math.min(minCost, currCost);
        } while (nextPermutation(nodes));

        return minCost;
    }

    static boolean nextPermutation(List<Integer> nodes) {
        int i = nodes.size() - 2;
        while (i >= 0 && nodes.get(i) >= nodes.get(i + 1)) {
            i--;
        }

        if (i < 0) {
            return false;
        }

        int j = nodes.size() - 1;
        while (nodes.get(j) <= nodes.get(i)) {
            j--;
        }

        Collections.swap(nodes, i, j);
        Collections.reverse(nodes.subList(i + 1, nodes.size()));
        return true;
    }

    public static void main(String[] args) {
        int[][] cost = {
            { 0, 10, 15, 20 },
            { 10, 0, 35, 25 },
            { 15, 35, 0, 30 },
            { 20, 25, 30, 0 }
        };

        int res = tsp(cost);
        System.out.println("Minimum TSP cost: " + res);
    }
}
