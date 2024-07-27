## LeetCode
### [743. Network Delay Time](https://leetcode.com/problems/network-delay-time/)
```python
import heapq

class Solution:

def networkDelayTime(self, times: List[List[int]], n: int, k: int) -> int:
	adj = defaultdict(list)
	for [src, tgt, time] in times:
		adj[src].append((tgt, time))
	
	def dijkstra(src: int) -> List[int]:
		min_time_list = [-1 for _ in range(n+1)]
		queue = [(0, src)]
		heapq.heapify(queue)
		while queue:
			time, curr = heapq.heappop(queue)
			if min_time_list[curr] != -1:
				continue
			min_time_list[curr] = time
			for nei, nei_time in adj[curr]:
				heapq.heappush(queue, (time+nei_time, nei))
		return min_time_list
	
	max_min = -1
	for time in dijkstra(k)[1:]:
		if time == -1:
			return -1
		if time > max_min:
			max_min = time
	
	return max_min
```

### [2093. Minimum Cost to Reach City With Discounts](https://leetcode.com/problems/minimum-cost-to-reach-city-with-discounts/)
```python 
class Solution:
    def minimumCost(self, n: int, highways: List[List[int]], discounts: int) -> int:
        adj = defaultdict(list)
        for [city1, city2, toll] in highways:
            adj[city1].append((city2, toll))
            adj[city2].append((city1, toll))

        def dijkstra(src):
            min_costs = [[ math.inf for _ in range(discounts+1)] for _ in range(n)]
            # Min-heap priority queue to store tuples of (cost, city, discounts used)
            heap = [(0, src, 0)]
            while heap: 
                cost, city, dis = heapq.heappop(heap)
                if min_costs[city][dis] != math.inf:
                    continue 
                min_costs[city][dis] = cost
                for nei, nei_cost in adj[city]:
                    heapq.heappush(heap, (cost+nei_cost, nei, dis))
                    if dis<discounts:
                        heapq.heappush(heap, (cost+nei_cost//2, nei, dis+1))
            return min_costs

        ans = min(dijkstra(0)[-1])
        if ans == math.inf:
            return -1
        return ans 
```