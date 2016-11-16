# ShaderLab

## 1. hello, world
    ```
    Shader "Custom/HelloWorld" {
      SubShader {
            pass {
                color(1, 1, 1, 1)
           }
      }
    }
    ```

## 2. 历史
* 作者 Unity
* 设计初衷 Unity中的shader语言，Unity在背后会根据使用的平台把这些结构编译成真正的代码和shader文件。

## 3. 编程范型
* 声明式

## 4. 语义(semantics)

### 4.1 应用阶段传递模型数据给顶点着色器阶段
* POSTION 模型空间的顶点位置 float4
* NORMAL 顶点法线 float3
* TANGENT 顶点切线 float4
* TEXCOORDn 顶点纹理坐标 float2 或者 float4
* COLOR 顶点颜色 fixed4 float4

### 4.2 顶点着色器传递数据给片元着色器阶段
* SV_POSTION 裁剪空间中的顶点坐标
* COLOR0 COLOR1 输出第一／二组顶点的颜色
* TEXCOORD0-7 输出纹理坐标

### 4.3 片元输出阶段
* SV_Target 输出值会存储到渲染目标中

## 5. 数据类型

## 5.1 结构
```
Shader "name" { 
    [Properties] 
    Subshaders 
    [Fallback] 
    [CustomEditor] 
}
```
