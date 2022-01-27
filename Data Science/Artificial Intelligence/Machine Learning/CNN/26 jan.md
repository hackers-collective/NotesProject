Recent class we understand cnn how it works by all steps include D.S img ,convolve(featureselection), poling(squizewithoutlooseinfo), flattering(2d to 1d), feature laye(all featuresx1x2x3..), N.N, final y
duty of cnn to findmain features for better feture=better acuracy and we have save time-possible wen less feture
we put data again again in convolve then poling to better result also swize decrease but multiple time it will lose quality 
so we do multiple time data to convolve .. then it fid main feature after we satisfied we poling it not lose info and might convolve 
so now we give data to flattering so it quickly do task bcs edges are amplified

lots of do hit and trial methode do-convolve convolve poling convolve convolve poling.....after may be other they get ressult and published research paper with that dataset to better occuracy
LeNet and AlexNet 

while kernal put kernal rendomly then multipley if any -ve values come so it affect data(img corrupt) after no mean to conver -ve to +ve bcs this proc have lots of color(0-255) so we put 0(no mean)rether use any -ve no. this is Relu() which is activation()
relu is hidden layer but we use this in layer 
sampling=poling
