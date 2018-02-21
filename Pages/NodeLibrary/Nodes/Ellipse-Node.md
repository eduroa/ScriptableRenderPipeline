## Description

Generates an ellipse shape based on input **UV** at the size specified by inputs **Width** and **Height**. The generated shape can be offset or tiled by connecting a [Tiling And Offset Node](https://github.com/Unity-Technologies/ShaderGraph/wiki/Tiling-And-Offset-Node). Note that in order to preserve the ability to offset the shape within the UV space the shape will not automatically repeat if tiled. To achieve a repeating dot effect first connect your input through a [Fraction Node](https://github.com/Unity-Technologies/ShaderGraph/wiki/Fraction-Node).

## Ports

| Name        | Direction           | Type  | Binding | Description |
|:------------ |:-------------|:-----|:---|:---|
| UV      | Input | Vector 2 | UV | Input UV value |
| Width      | Input | Vector 1 | None | Ellipse width |
| Height      | Input | Vector 1 | None | Ellipse height |
| Out | Output      |    Vector 1 | None | Output value |

## Shader Function

```
UV = (UV * 2.0 - 1.0);
UV = UV / float2(Width, Height);
Out = step(length(UV), 1);
```