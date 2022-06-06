# 3D Taylor Green Vortex Simulation in Julia

![taylor_green_animation](https://user-images.githubusercontent.com/27728103/172134850-c7268c46-3443-4295-a937-ee44ca535a3c.gif)

📺 Watch a [4K video of this](https://youtu.be/7dDAlm35ftM).

🔁 A pseudo-spectral solver for the 3D Taylor-Green Vortex using the Fast Fourier Transformation (FFT) ⚡. The implemenation is based on the [Spectral DNS in Python Repo](https://github.com/spectralDNS/spectralDNS).

The 3D Taylor Green Vortex is a common test case for Direct Numerical Simulation of Turbulence. Due to its 3D periodic domain it is a perfect candidate for a pseudo-spectral solver that allows for fine discretizations at manageable computational cost (due to the *N log(N)* scaling properties of the FFT) 👍.

You can [watch a code-along implementation](https://youtu.be/QNJeWgVLML8) here.

The Taylor Green Vortex builds upon the (incompressible) Navier-Stokes equations:


    ∂u/∂t + (u ⋅ ∇) u = − 1/ρ ∇p + ν ∇²u + f
    ∇ ⋅ u = 0

The domain is:

    Ω = (0, 2π)³

For the Taylor-Green Vortex we have the following simplifications:

    ρ = 1
    f = 0

The kinematic viscosity is set to:

    ν = 1/1600

The crucial incredient to the Taylor Green Vortex is the initial condition:

    u(t=0, x, y, z) =   sin(x)cos(y)cos(z)
    v(t=0, x, y, z) = − cos(x)sin(y)cos(z)
    w(t=0, x, y, z) = 0

This initial state results in many stages all the way to full turbulence and, finally, a dissipation and decay.

👉 Also check out the [Repo](https://github.com/Ceyron/machine-learning-and-simulation) of my [YouTube Channel](https://www.youtube.com/c/MachineLearningSimulation) for similar simple simulation scripts in Julia and Python.
