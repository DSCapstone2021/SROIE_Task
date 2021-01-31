# SROIE_Task
figure out how to organize the data (into a dataframe)

    - need to separate into 4 different processes (one for each question asked)
    - y column would be a boolean for whether that text is the answer for the question asked
    - X column potentials: coordinates, area of textbox (%), y_range (%), x_range (%), label, type ['float', 'date-format', etc.]
        - how to align our boxes for x/y ranges

MVP 0

Approach: Locate lowest label containing "TOTAL", and identify right-most monetary value as 'total'

Implementation: Brute force

Pros: Super simple & serves as a guide in brainstorming our neural network. More coontrol over circumstances.

Cons: Doesn't take into account any other variables which can help identify 'total'. 
Ignores the 'teach AI to do math' project goal

Testing:

Performance: 

Notable Mention: X00016469619.txt - doesn't have 'total' located anywhere near the actual total



MVP 1

y-axis 

filter out non-floats

filter out smaller area totals

MVP 2

check that the math works out between the different numbers present in the invoice






# Different Approaches:

1) Train a NN to recognize the bounds of the total value, and then train another one to get the number from the bounds.

Pros: We would be first guiding the network to recognize the bounds, which could be really good if we find the right loss function. Once we have the bounds, getting the number should be a simple task. Could actually work very well if we get the right training data. To test it we could just use the testing data values for "Total".

Cons: We don't have training data for our first network. Although we could use the boxes from task 1, it's hard to know which box has the total value. A possible solution would be similar to the one above. Look for the word total and make the value of it be the rightmost box aligned with the word.

2) Train a NN to recognize the total value directly.

Pros: We already have the data for this since we have the images and we have the totals.

Cons: It's hard to think this could work because we are giving very little guidance. Also, we would probably need way more data than just 600 images.

3) Train a NN to recognize the rectangle that contains the word describing total (Total, amount due, etc) and the corresponding value.

Pros: It might find it easier to learn this since now it can look for patterns in the word but also in the numbers. It also has a humanlike approach since usually before paying we look at that rectangle that contains the word total and the value of it.

Cons: We don't have data with this information.


