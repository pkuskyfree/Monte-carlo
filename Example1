#    A Sample Monte Carlo Simulation 

clc <- function() cat(rep("\n",50))   #Create an R function that can be used to clear the screen
clc()

Num = 100                             # Number of random cases for Monte Carlo model
set.seed(123459)                      # Usethis to make the randomly generated data the same ueach time you run the simulation.
                                      # Change the 123459 to another large integer to chnage the sequence.
                                      # Omit line to have a truly random sequence of numbers each time you run it.

rnorm(Num)                            # generates 100 random normally distributed numbers (since Num=100)
e<- rnorm(Num, mean=0, sd=1)          # Stores 100 random normally distributed numbers with Mean=0 and SD=1 in varable e.
e                                     # Writes variable e to the screen
e2<- rnorm(Num, mean=0, sd=1)         # Creates another variable like e, but different random numbers

hist(e,freq=FALSE,nclass=100)         # Draws histogram of e.  R code below puts lines showing actual and theoretical distribution on histogram
x=seq(min(e),max(e),len=200)
lines(x,dnorm(x, mean=0, sd=1),col=2, lty=2, lwd=3)     #use Help on par to find graphics parameteres
lines(x,dnorm(x,mean=mean(e),sd=sqrt(var(e))))

X1<-runif(Num,0,100)                  # Generates a random uniform variable X1 with values between 0 and 100.
hist(X1,freq=FALSE,nclass=100)        # Draws histogram of X1
X2<-runif(Num,0,100)                  # Another random uniform variable

                                      # Specify the parameters for a linear model
B0<- 2                                # a (the Intercept)
B1<-2                                 # B1 Cthe coefficient for X1)
B2<-2                                 # B2 (the Coefficient for X2)


Scale=100                             # Select a weight to increase/decrease error variace - for adjusting goodness of fit and image

Y1<- B0+B1*X1+B2*X2+Scale*e           # Generate the dependent variable, based on the data generated and the model selected.
hist(Y1,freq=FALSE,nclass=100)        # Plot histogram of dependent variable

plot(X1, Y1, xlab="X1", ylab="Y")     # Plot X by Y

                                     
Mod.X2<-lm(Y1~X1+X2)                  # Run Regression (OLS) storig results in an oject called Mod.X2
summary(Mod.X2)                       # Write out model information
