# Midterm
 
Part 1
When making the Dr. Mario game, I added a simple animation to mimic the player getting 4 cells in a row, similar to the example given. I created 4 cells of the same color and 1 cell that was different. I also made sure the cells had different textures to give varying cells. 

Part 2
I added a toon shader to the pages on the notebook as it made the paper look more like paper with less shading on the sides of the pages.

I used this code to insure that the difference in shades in the paper would be larger and the paper could look more like paper:

float4 LightingToonRamp (SurfaceOutput s, fixed3 lightDir, fixed atten)
{
    float diff = dot (s.Normal, lightDir);
    float h = diff * .3 + 0.3;
    float2 rh = h;
    float3 ramp = tex2D(_RampTex, rh).rgb;

    float4 c;
    c.rgb = s.Albedo * _LightColor0.rgb * (ramp);
    c.a = s.Alpha;
    return c;
}

Part 3
To make the scene look more like a hospital, I created a white background with cool colors and a red hospital logo at the top. For the background, I used a specular shader to give the white wall a pinkish tint.

Part 4
I added a hologram shader to my game for two uses: The first use is for the hospital logo to give a glow and make it look like a neon sign. The other use was is applied when the player gets 4 cells aligned, the game turns the 4 cells into holograms to clearly show that they are being eliminated.