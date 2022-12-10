
# Reference Video
[Basic Shader Code Template](https://www.youtube.com/watch?v=gY1Mx4kkZPU)
[Knowledgeable Source on HLSL & Shader Graph](https://www.cyanilux.com/contents/)


# Template

```HLSL
Shader "Unlit/ExampleShader"
{
	Properties
	{
		_MainTex ("Texture", 2D) = "white" {}
	}
	SubShader
	{
		Tags { "RenderType"="Opaque"}
		LOD 100

		HLSLINCLUDE
		#include "Packages/com.unity.render-piplines.universal/ShaderLibrary/Core.hlsl"
	
		CBUFFER_START(UnityPerMaterial)
			float4 _BaseColor;
		CBUFFER_END
	
		TEXTURE2D(_MainTex);
		SAMPLER(sampler_MainTex);
	
		struct VertexInput
		{
			float4 position : POSITION;
			float2 uv : TEXTCOORD0;
		};
	
		struct VertexOutput
		{
			float4 position : SV_POSITION;
			float2 uv : TEXCOORD0;
		};
	
		ENDHLSL
	
		Pass 
		{
			HLSLPROGRAM
			#pragma vertex vert
			#pragma fragment frag
	
			VertexOutput vert(VertexInput i)
			{
				VertexOutput o;
				o.position = TransformObjectToHClip(i.position.xyz);
				o.uv = i.uv;
				return o;
			}
	
			float4 frag(VertexOutput i) : SV_Target
			{
				float4 baseTex = SAMPLE TEXTURE2D(_MainTex, sampler_MainTex, i.uv);
				return baseTex * _BaseColor;
			}
			ENDHLSL
		}


	}
}
```