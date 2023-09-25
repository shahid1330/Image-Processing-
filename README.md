# Image-Processing-
**negative**

<br>img=imread('cameraman.tif');
<br>[m,n]=size(img);
<br>negative=zeros(m,n);
<br>for i= 1 : m
    <br>&nbspfor j= 1: n
        <br>img(i,j)=255-img(i,j);
    <br>end
<br>end
<br>imshow(img);

**log transformation**

img=imread('cameraman.tif');
[m,n]=size(img);
c=29;
for i= 1 : m
    for j= 1: n
        img(i,j)=c*log(255+double( img(i,j) ) );
    end
end
imshow(img);

**gamma 2 variable transformation**

img=imread('cameraman.tif');
[m,n]=size(img);
c=2;
g=1;
for i= 1 : m
    for j= 1: n
        img(i,j)= c * (double(img(i,j))^g);
    end
end
imshow(img);

**intensity level slicing**

img=imread('moon.tif');
[m,n]=size(img);
for i = 1 : m
    for j = 1 : n
        if (img(i,j)<110)
            img(i,j)=255;
        end    
    end    
end
imshow(img);
