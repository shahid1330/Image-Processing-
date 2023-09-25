# Image-Processing-
**negative**

<br>img=imread('cameraman.tif');
<br>[m,n]=size(img);
<br>negative=zeros(m,n);
<br>for i= 1 : m
    <br>for j= 1: n
        <br>img(i,j)=255-img(i,j);
    <br>end
<br>end
<br>imshow(img);

**log transformation**

<br>img=imread('cameraman.tif');
<br>[m,n]=size(img);
<br>c=29;
<br>for i= 1 : m
    <br>for j= 1: n
        <br>img(i,j)=c*log(255+double( img(i,j) ) );
    <br>end
<br>end
<br>imshow(img);

**gamma 2 variable transformation**

<br>img=imread('cameraman.tif');
<br>[m,n]=size(img);
<br>c=2;
<br>g=1;
<br>for i= 1 : m
    <br>for j= 1: n
        <br>img(i,j)= c * (double(img(i,j))^g);
    <br>end
<br>end
<br>imshow(img);

**intensity level slicing**

<br>img=imread('moon.tif');
<br>[m,n]=size(img);
<br>for i = 1 : m
    <br>for j = 1 : n
        <br>if (img(i,j)<110)
            <br>img(i,j)=255;
        <br>end    
    <br>end    
<br>end
<br>imshow(img);
