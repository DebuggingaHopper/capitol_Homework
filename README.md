# capitol_Homework

A Repository where I will store all Homework assignments for Advanced Machine Learning held at Capitol Technology University

## HW 1

My initial experiment for the first homework was to utilize the equation to convert pounds to kilograms. It is important to remember that to convert pounds to kilograms we would need to divide the value in pounds by  2.205. 

To begin the process I wanted to utilize a data set of around 10 values in pounds and kilograms respectively to ensure we can have a decent starting set.
(![image](https://github.com/DebuggingaHopper/capitol_app_Git/assets/49813790/490a6450-e16e-4278-bc5f-47de4c7bfce8)

Once we have done that I am now establishing my 1 input neuron and 1 output neuron through the following code:

![image](https://github.com/DebuggingaHopper/capitol_app_Git/assets/49813790/a337c0c1-ca7e-419b-ae5d-066d21e01333)

What I also did was utilize varying values for the epochs & Adams value however by making the epoch value too large I realized that I was making more room for error due to the loss fluctuating to the point it was increasing due to the mass amount of Epochs.

What this helped me to understand is that establishing an adequate value for the epoch is essential to ensure that the loss value does not begin to fluctuate to the point that it's increasing when it should not be. Furthermore, I also tampered with the Adams value but noticed too few values caused my value for m in regards to the mx+b equation to be a bit off compared to what I desired from my current Adaams family. the accuracy is a bit less however the accuracy of the m values with respect to the mx+b equation was crucial for me to fully understand that even though accuracy was impacted, it's essential to ensure that the values that are heavily relied upon for correctly calculating the data is set to a reasonable value. This helped me understand a bit more of what is needed to understand when setting up these input and output layers.

Now within the following code, we are able to visually see how drastically the loss value decreases due to our epochs:

![image](https://github.com/DebuggingaHopper/capitol_app_Git/assets/49813790/2240402b-d7fd-4ae8-81ac-3bc31e164708)

I noticed that decreasing the number of epochs also would cause issues displaying why our current value is ideal in this scenario. We can also see that we are able to accurately get the value of 100 pounds which is 45.3592

To conclude we are finally able to see our weight which is 4535916 which is  equivalent to 0.453592 which is the value of when we convert 1 pound to 1 kilogram. this demonstrated our neural network was able to get an accurate weight since 1 pd is 0.453592 . Our Bias is as close to 0 since there is no additional bias present in this conversion formula. What we have demonstrated is a clear understanding of how to create this network and an understanding what occurs throughout this process.
![image](https://github.com/DebuggingaHopper/capitol_app_Git/assets/49813790/a514e5be-5092-4e98-8ac7-dd3fe9b0643a)




