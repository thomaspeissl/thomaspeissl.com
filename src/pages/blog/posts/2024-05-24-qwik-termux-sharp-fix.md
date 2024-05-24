--- 
title: "How to fix Qwik Framework Sharp Error on Termux"
description: "Use one npm command to get the Qwik framework up and running on your Android device."
published: 2024-05-24
layout: ../../../layouts/BlogPostLayout.astro 
---

Note that this works for me on my armv8l device.

## The fix

The error you might see for the `npm start` command:

*Error: Could not load the "sharp" module using the android-arm runtime*

Luckily, there is an easy fix for this error:

`npm install --cpu=wasm32 sharp`

After running this command, your `npm start` should work fine.
