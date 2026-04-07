---
title: Algorithm Notes
tags: [reference, cs]
---
# Algorithm Notes

Quick reference for common algorithms with math notation and code.

## Big-O Complexity

| Algorithm | Time | Space |
| --- | --- | --- |
| Binary Search | O(log⁡n)O(\log n)O(logn) | O(1)O(1)O(1) |
| Merge Sort | O(nlog⁡n)O(n \log n)O(nlogn) | O(n)O(n)O(n) |
| Quick Sort | O(nlog⁡n)O(n \log n)O(nlogn) avg | O(log⁡n)O(\log n)O(logn) |
| BFS/DFS | O(V+E)O(V + E)O(V+E) | O(V)O(V)O(V) |
| Dijkstra | O(Elog⁡V)O(E \log V)O(ElogV) | O(V)O(V)O(V) |

## Binary Search

The key idea: repeatedly halve the search space. Time complexity is O(log⁡n)O(\log n)O(logn).

```python
def binary_search(arr, target):
    lo, hi = 0, len(arr) - 1
    while lo <= hi:
        mid = (lo + hi) // 2
        if arr[mid] == target:
            return mid
        elif arr[mid] < target:
            lo = mid + 1
        else:
            hi = mid - 1
    return -1
```

## Math Formulas 

### Inline Math

Euler's identity: eiπ+1=0e^{i\pi} + 1 = 0eiπ+1=0

The golden ratio: φ=1+52≈1.618\varphi = \frac{1 + \sqrt{5}}{2} \approx 1.618φ=21+5​​≈1.618

Pythagorean theorem: a2+b2=c2a^2 + b^2 = c^2a2+b2=c2

### Block Math

The quadratic formula:

x=−b±b2−4ac2ax = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a} x=2a−b±b2−4ac​​

Summation of first nnn natural numbers:

∑i=1ni=n(n+1)2\sum_{i=1}^{n} i = \frac{n(n+1)}{2} i=1∑n​i=2n(n+1)​

Bayes' theorem:

P(A∣B)=P(B∣A)⋅P(A)P(B)P(A|B) = \frac{P(B|A) \cdot P(A)}{P(B)} P(A∣B)=P(B)P(B∣A)⋅P(A)​

Normal distribution:

f(x)=1σ2πe−12(x−μσ)2f(x) = \frac{1}{\sigma\sqrt{2\pi}} e^{-\frac{1}{2}\left(\frac{x-\mu}{\sigma}\right)^2} f(x)=σ2π​1​e−21​(σx−μ​)2

Matrix multiplication:

Cij=∑k=1nAik⋅BkjC_{ij} = \sum_{k=1}^{n} A_{ik} \cdot B_{kj} Cij​=k=1∑n​Aik​⋅Bkj​

### Calculus

Derivative definition: f′(x)=lim⁡h→0f(x+h)−f(x)hf'(x) = \lim_{h \to 0} \frac{f(x+h) - f(x)}{h}f′(x)=limh→0​hf(x+h)−f(x)​

Fundamental theorem of calculus:

∫abf(x) dx=F(b)−F(a)\int_a^b f(x)\,dx = F(b) - F(a) ∫ab​f(x)dx=F(b)−F(a)

## Sorting — Merge Sort

Divides array in half, sorts each, merges. Stable sort with O(nlog⁡n)O(n \log n)O(nlogn) guaranteed.

```javascript
function mergeSort(arr) {
  if (arr.length <= 1) return arr;
  const mid = Math.floor(arr.length / 2);
  const left = mergeSort(arr.slice(0, mid));
  const right = mergeSort(arr.slice(mid));
  return merge(left, right);
}

function merge(a, b) {
  const result = [];
  let i = 0, j = 0;
  while (i < a.length && j < b.length) {
    result.push(a[i] <= b[j] ? a[i++] : b[j++]);
  }
  return result.concat(a.slice(i), b.slice(j));
}
```

## Graph — Dijkstra's Algorithm

Shortest path from source to all vertices. Uses a priority queue. Complexity: O(Elog⁡V)O(E \log V)O(ElogV).

```rust
fn dijkstra(graph: &Vec<Vec<(usize, u64)>>, start: usize) -> Vec<u64> {
    let n = graph.len();
    let mut dist = vec![u64::MAX; n];
    let mut heap = BinaryHeap::new();
    dist[start] = 0;
    heap.push(Reverse((0, start)));
    while let Some(Reverse((cost, u))) = heap.pop() {
        if cost > dist[u] { continue; }
        for &(v, w) in &graph[u] {
            if dist[u] + w < dist[v] {
                dist[v] = dist[u] + w;
                heap.push(Reverse((dist[v], v)));
            }
        }
    }
    dist
}
```

## Related

See [[projects/noctodeus-roadmap]] for how the FTS5 search algorithm works in Noctodeus. See [[feature-showcase]] for all editor features including tables and code blocks.
