###### 1. The following code is written in C, where elements of an array are allocated contiguously. Arrays `a` has 1024 $\times$ 1024 elements. Arrays `b` and `c` have 1024 elements respectively. Assume each element of arrays is a 4-byte (32-bit) integer. The data type of all variables is a 4-byte integer also. Cache blocks are allocated on write miss, and the size of a cache line is 64 bytes. Assume the cache size is infinite (what?). *(Hint: in this code, there are 6 variables: a,b,c,i,j, and sum)* 
```C
int sum;
for (int i = 0; i < 1024; i++)
{
	sum = 0;
	for (int j = 0; j < 1024; j++)
		sum += a[j+i*1024] + b[j];
	c[i] = sum;
}
```
(a) Which variable references exhibit temporal locality?
**Sol)**
`sum`, `i`, `j`, and array `b`.

(b) Which variable references exhibit spatial locality?
**Sol)**
arrays `a`, `b`, and `c`.

(c) Let's focus on the data transfers for arrays `a`, `b`, and `c`. How many `lw` and `sw` instructions are issued while executing this code?
**Sol)**
Array `a`: 1,048,576 `lw`
Array `b`: 1,048,576 `lw`
Array `c`: 1,024 `sw`

(d) Let's focus on the cache miss rates for arrays `a`, `b`, and `c`. Calculate the miss rate for arrays. *(Hint: we assume the cache size is infinite. Cache is initially empty).*
**Sol)**
Miss rate of `a`: $1 / 16 = 6.25\%$
Miss rate of `b`: $64 / 1,048,576 \approx 0.006\%$
Miss rate of `c`: $1 / 16 = 6.25\%$
###### 2. Below is a list of 64-bit memory address references, given as **word addresses**. (1 word = 4 bytes)
```
0xFD, 0xBA, 0x2C, 0xB5, 0x0E, 0xBE, 0x58, 0xBF, 0x02, 0x2B, 0xB4, 0x03
```
(a) Let us assume a direct-mapped cache has 16 blocks and a single block includes 4 word. What is the size of this cache?
**Sol)**
The total number of words in cache = 64 words. Therefore, the size of cache is $64\times 4 = 256$ bytes.

(b) For each of these references, identify the binary word address, the tag and the index given a direct-mapped cache with 16 **four-word** blocks (i.e. the cache has 16 blocks, and the size of a single block is four words.) Also list whether each reference is a hit or miss, assuming the cache is initially empty.
**Sol)**

| Word address | Binary address | Tag | Index | Hit/Miss |
| :----------: | :------------: | :-: | :---: | :------: |
|    `0xFD`    |   1111 1101    | 11  | 1111  |   Miss   |
|    `0xBA`    |   1011 1010    | 10  | 1110  |   Miss   |
|    `0x2C`    |   0010 1100    | 00  | 1011  |   Miss   |
|    `0xB5`    |   1011 0101    | 10  | 1101  |   Miss   |
|    `0x0E`    |   0000 1110    | 00  | 0011  |   Miss   |
|    `0xBE`    |   1011 1110    | 10  | 1111  |   Miss   |
|    `0x58`    |   0101 1000    | 01  | 0110  |   Miss   |
|    `0xBF`    |   1011 1111    | 10  | 1111  |   Hit    |
|    `0x02`    |   0000 0010    | 00  | 0000  |   Miss   |
|    `0x2B`    |   0010 1011    | 00  | 1010  |   Miss   |
|    `0xB4`    |   1011 0100    | 10  | 1101  |   Hit    |
|    `0x03`    |   0000 0011    | 00  | 0000  |   Hit    |
(c) Calculate the hit rate (in percentage) of the above cache.
**Sol)**
$\text{Hit rate} = 3 / 12 =25\%$.

(d) Let us assume that the size of a single block is increases to **eight words** while the size of the direct-mapped cache is the **same**. For each these references, identify the binary word address, the tag, and the index. Also list if each reference is a hit or a miss, assuming the cache is initially empty.
**Sol)**
Note that size of cache is still 64 words, so, the number of block is 8 blocks in cache and block size is 8 words. Index bit is $\log_{2}(8) = 3$, and Offset bit is $\log_{2}(8)=3$. Tag bit is $8-3-3 = 2$ bits.

| Word address | Binary address | Tag | Index | Hit/Miss |
| :----------: | :------------: | :-: | :---: | :------: |
|    `0xFD`    |   1111 1101    | 11  |  111  |   Miss   |
|    `0xBA`    |   1011 1010    | 10  |  111  |   Miss   |
|    `0x2C`    |   0010 1100    | 00  |  101  |   Miss   |
|    `0xB5`    |   1011 0101    | 10  |  110  |   Miss   |
|    `0x0E`    |   0000 1110    | 00  |  001  |   Miss   |
|    `0xBE`    |   1011 1110    | 10  |  111  |   Hit    |
|    `0x58`    |   0101 1000    | 01  |  011  |   Miss   |
|    `0xBF`    |   1011 1111    | 10  |  111  |   Hit    |
|    `0x02`    |   0000 0010    | 00  |  000  |   Miss   |
|    `0x2B`    |   0010 1011    | 00  |  101  |   Hit    |
|    `0xB4`    |   1011 0100    | 10  |  110  |   Hit    |
|    `0x03`    |   0000 0011    | 00  |  000  |   Hit    |
(e) Calculate the hit rate (in percentage) of the above cache.
**Sol)**
$\text{Hit rate}=5 / 12 \approx 41.67\%$

###### 3. For a direct-mapped cache design with a 32-bit address, the following bits of the address are used to access the cache. (1 word = 4 bytes)

|  Tag  | Index | Offset |
| :---: | :---: | :----: |
| 31-11 | 10-5  |  4-0   |

(a) What is the cache block size (in words)?
**Sol)**
Offset bits = 5. So, block size in bytes $2^{5} = 32\text{ bytes}$. So, Block size in words is $8\text{ words/block}$.

(b) How many blocks does the cache have?
**Sol)**
Index bits = 6. So, the number of blocks are $2^{6}=64$ blocks.

(c) What is the ratio between total bits required for such a cache implementation over the data storage bits? Let us assume each cache block includes 1-bit "valid" field.
**Sol)**
We need to consider both the data storage and the overhead(tag + valid).
1. Data storage bits
$\text{Total data bits} = 64 \text{ blocks}\times 8\text{ words/block}\times 32 \text{ bits/word} = 16384 \text{ bits}$
2. Overhead bits
$\text{Total overhead} = 64\text{ blocks}\times (21 + 1)\text{ bits/block}=1408\text{ bits}$

Hence,
$$
\frac{\text{Total bits}}{\text{Data bits}}=\frac{16384+1408}{16384}=\frac{17792}{16384}\approx 1.0859
$$
In other words, total bits are $8.59\%$ more than the data bits alone.
###### 4. Let us assume that a pipelined processor is composed of 5-state of pipelining. This processor works with $1\text{ GHz}$ clock. The processor includes two types of L1 caches: L1 instruction (L1-I) cache and L1 data (L1-D) cache. When a cache miss occurs, requested words are transferred from a main memory with the latency of (100+8W) ns, where W means the number of words (1 word = 4 bytes). Following table shows the organization of L1-I and L1-D caches.

|      Cache      | Total size | Associativity | Block size | Miss rate | Hit time |
| :-------------: | :--------: | :-----------: | :--------: | :-------: | :------: |
| L1 instructions |    8 KB    |     2-way     |  4 words   |    2%     |  0.8ns   |
|     L1 data     |    8 KB    |     4-way     |  2 words   |    8%     |  0.95ns  |
The following table shows the breakdown of instructions.

| Arithmetic/logic | Load | Store | Branch | Jump |
| :--------------: | :--: | :---: | :----: | :--: |
|       52%        | 25%  |  10%  |  11%   |  2%  |
(a) Compute AMAT (average memory access time) of each cache (in cycles).
**Sol)**
Note that clock is $1\text{ GHz}$, So, $1\text{ Cycle}= 1\text{ ns}$.
L1-I cache:
$\text{Block size} = 4 \text{ words}\rightarrow W=4$
$\text{Miss penalty}=100+8W = 100+32=132 \text{ ns}=132 \text{ cycles}$
$\text{AMAT}_{\text{I}} = \text{Hit time}+\text{Miss rate}\times \text{Miss penalty}=0.8+0.02\times 132=\boxed{ 3.44 \text{ cycles} }$

L1-D cache:
$\text{Block size} = 2 \text{ words}\rightarrow W=2$
$\text{Miss penalty}=100+8W = 100+16=116 \text{ ns}=116 \text{ cycles}$
$\text{AMAT}_{\text{D}} = \text{Hit time}+\text{Miss rate}\times \text{Miss penalty}=0.95+0.08\times 116=\boxed{ 10.23 \text{ cycles} }$

(b) Assuming the base CPI of the processor is 1.0 without any stalls by cache misses, what is the total CPI?
**Sol)**
We assume that stall occurs independently.
L1-I cache miss stall: $0.02\times 132 = 2.64 \text{ cycles}$
L1-D cache miss stall: $0.35\times 0.08 \times 116= 3.248\text{ cycles}$
$$
\begin{align}
\text{Total CPI} &= \text{Base}+\text{I-cache stall}+\text{D-cache stall} \\
&=1.0+2.64+3.248 \\
&=6.888\text{ cycles/instruction} \\
\end{align}
$$

(c) Cache block size can influence the miss rate and miss penalty. Note that memory transfer latency is (100+8W) ns. Following table shows the miss rates by various block size of the L1-D cache. What is the optimal block size of the L1-D cache that can exhibit the best performance?

| **Block size** | 2 words | 4 words | 8 words | 16 words | 32 words |
| -------------- | ------- | ------- | ------- | -------- | -------- |
| **Miss rate**  | 8%      | 6%      | 4%      | 3%       | 2%       |
**Sol)**
1. Block size: 2 words
$\text{AMAT}_{\text{D}} = \text{Hit time}+\text{Miss rate}\times \text{Miss penalty}=0.95+0.08\times 116=10.23$
2. Block size: 4 words
$\text{AMAT}_{\text{D}} = \text{Hit time}+\text{Miss rate}\times \text{Miss penalty}=0.95+0.06\times 132=8.87$
3. Block size: 8 words
$\text{AMAT}_{\text{D}} = \text{Hit time}+\text{Miss rate}\times \text{Miss penalty}=0.95+0.04\times 164=7.51$
4. Block size: 16 words
$\text{AMAT}_{\text{D}} = \text{Hit time}+\text{Miss rate}\times \text{Miss penalty}=0.95+0.03\times 228=7.79$
5. Block size: 32 words
$\text{AMAT}_{\text{D}} = \text{Hit time}+\text{Miss rate}\times \text{Miss penalty}=0.95+0.02\times 356=8.07$

So, Optimal block size is 8 words.

(d) Cache size can influence the miss rate and hit time of a cache. Let us assume that L1-D miss rate can be decreased to 5% and the hit time of the L1-D cache increases to 1.2 ns if the cache size doubles. Compute the speedup of this processor if L1-D cache size doubles (i.e. 16 KB). (Hint: As the hit time of the 16 KB cache is bigger than 1 ns, it determines the clock rate.)
**Sol)**
The pipeline frequency will be determined by the slowest stage (the cache).
Thus 1 cycle = 1.2 ns.
Now 1 cycle = 1.2 ns, so miss penalty in cycles $= 132\text{ ns} / 1.2 \text{ ns} = 110\text{ cycles}$.
I-cache hit time $=0.8\text{ ns} < 1.2\text{ ns}$, so it fits in 1 cycle.
Assume block size is same(2 words), so miss penalty in cycles $=116 / 1.2 \approx 96.67\text{ cycles}$. L1-D hit time $= 1.2\text{ ns}=1\text{ cycle}$.
$$
\begin{align}
\text{I stall} &= 0.02\times \frac{132}{1.2} = 2.2\text{ Cycles/Inst} \\
\text{D stall} &=0.35\times0.05\times \frac{116}{1.2}\approx 1.6917\text{ Cycles/Inst} \\
\text{Total CPI} &\approx 1+2.2+1.6917=4.8917\text{ Cycles/Inst}
\end{align}
$$
$$
\begin{align}
\text{Performance}_{\text{original}} &= 6.888 \times 1 = 6.888\text{ ns/Inst}\\ 
\text{Performance}_{\text{new}}  &= 4.8917\times 1.2 = 5.87\text{ ns/Inst} \\
\text{Speedup} &= \frac{\text{Performance}_{\text{original}}}{\text{Performance}_{\text{new}}}\approx 1.173
\end{align}
$$
So, about 17.3% improved.

###### 5. Let us assume that memory subsystem is configured as follows.
Size of virtual address = 20-bits, size of physical address = 16-bits
Word size = 4 byte, page size = 4 KB
L1 cache: direct-mapped, 4 words/block, 4 entries
L1 TLB: direct-mapped, 2 entries
![[assignment4figure.png|center]]
When a memory instruction is executed, the processor first accesses the L1 TLB to translate virtual address into physical address. Then the L1 cache is accessed using the physical addresses.

(a) What is the maximum size of the virtual memory supported by this system?
**Sol)**
$2^{20} \text{ bytes} = 1\text{ MB}$.

(b) What is the size of the physical memory?
**Sol)**
$2^{16} \text{ bytes} = 64\text{ KB}$.

(c) What is the size of the virtual page number (VPN)?
**Sol)**
We have 20-bit virtual address and 4 KB=$2^{12}$ page size. The offset is $12$ bits, so the remaining top bits form the VPN, $8\text{ bits}$.

(d) Assuming the size of a single entry in the single-level page table is 4-byte, compute the size of the page table that resides in DRAM.
**Sol)**
$$
\begin{align}
\text{Total number of virtual pages} &= \frac{\text{Virtual memory size}}{\text{Page size}} \\
&= \frac{2^{20}}{2^{12}} = 2^{8}=256 \text{ entries} \\
\text{Total page table size} &= 256 \text{ entries}\times 4\text{ byte/entry} \\
&=1024\text{ bytes} = \boxed{ 1\text{ KB} }
\end{align}
$$

(e) Let us assume that the entries of the L1 TLB and the L1 cache are allocated as follows. (All address data are represented using hexadecimal numbers.)
* **L1 TLB**

| Valid |  Tag   |  PPN  |
| :---: | :----: | :---: |
|   1   | `0x04` | `0x4` |
|   1   | `0x30` | `0x8` |
* **Cache**

| Valid |   Tag   |
| :---: | :-----: |
|   1   | `0x100` |
|   1   | `0x203` |
|   1   | `0x3FF` |
|   1   | `0x118` |
Describe the operations of TLB and cache for the following load requests. The address of a load instruction is byte-address. You should justify your answers.
Example: lw 0x123456 $\to$ TLB hit, VPN=0x123 (tag=0x12, index=0x3) PPN=0x89, physical address = 0x89456; cache hit (tag: 0x894, index 0x5)

**Sol)**
(1) `lw 0x30FE0`$\to$TLB miss, VPN = `0x30` (tag=`0x18`, index=`0x0`)
(2) `lw 0x10004`$\to$TLB miss, VPN = `0x10` (tag=`0x08`, index=`0x0`)
(3) `lw 0x610E4`$\to$TLB hit, VPN=`0x61`(tag=`0x30`, index=`0x1`) PPN=`0x8`, physical address=`0x80E4`; cache miss (tag=`0x203`, index=`0x2`)
(4) `lw 0x610DC`$\to$TLB hit, VPN=`0x61`(tag=`0x30`, index=`0x1`) PPN=`0x8`, physical address=`0x80DC`; cache hit (tag=`0x203`, index=`0x1`)