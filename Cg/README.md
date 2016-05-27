# CG

## 1. 历史
* 作者 NVIDIA公司
* 设计初衷 GPU编程设计

## 4. 数据结构
1. float 32b
2. half 16b
3. fixed 12b
4. int 32b
5. bool
6. sampler * 

## 6. 流程控制

### 6.1 分支
```Cg
if(pos.x < 0 && pos.y < 0) {
    col = float4(1, 0, 0, 1);
} else if(pos.x < 0 && pos.y > 0){
    col = float4(0, 1, 0, 1);
} else if (pos.x > 0 && pos.y < 0) {
    col = float4(0, 0, 1, 1);
} else {
    col = float4(1, 1, 0, 1);
}
```

### 6.2 循环
```Cg
int i = 0;
while(i<10) {
    i++;
}
if(i==10)
    col = float4(0, 0, 0, 1);

i = 0;
do {
    i++;
} while (i < 20);
if(i == 20)
    col = float4(0, 1, 0, 1);

for(i=0; i < 1023; ++i) {}
if (i == 1023) 
    col = float4(0, 0, 1, 1);  
```

