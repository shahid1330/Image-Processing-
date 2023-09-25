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

**Sampling**

<br>I = imread('cameraman.tif');
<br>[m, n] = size(I);

<br>A = zeros(m/2, n/2);
<br>for i = 1:m/2
    <br>for j = 1:n/2
        <br>A(i, j) = I(2*i, 2*j);
    <br>end
<br>end

<br>B = zeros(m/4, n/4);
<br>for i = 1:m/4
    <br>for j = 1:n/4
        <br>B(i, j) = A(2*i, 2*j);
    <br>end
<br>end

<br>C = zeros(m/8, n/8);
<br>for i = 1:m/8
    <br>for j = 1:n/8
        <br>C(i, j) = B(2*i, 2*j);
    <br>end
<br>end

<br>D = zeros(m/16, n/16);
<br>for i = 1:m/16
    <br>for j = 1:n/16
        <br>D(i, j) = B(2*i, 2*j);
    <br>end
<br>end

<br>imshow(B, []);

**Quantization**

<br>I = imread('cameraman.tif');

<br>[m, n] = size(I);

<br>A = zeros(m, n);
<br>B = zeros(m, n);
<br>C = zeros(m, n);
<br>D = zeros(m, n);
<br>E = zeros(m, n);
<br>F = zeros(m, n);
<br>G = zeros(m, n);
<br>H = zeros(m, n);

<br>for i = 1:m
    <br>for j = 1:n
        <br>A(i, j) = 2 * (I(i, j) / 2);
        <br>B(i, j) = 4 * (I(i, j) / 4);
        <br>C(i, j) = 8 * (I(i, j) / 8);
        <br>D(i, j) = 16 * (I(i, j) / 16);
        <br>E(i, j) = 32 * (I(i, j) / 32);
        <br>F(i, j) = 64 * (I(i, j) / 64);
        <br>G(i, j) = 128 * (I(i, j) / 128);
        <br>H(i, j) = 256 * (I(i, j) / 256);
    <br>end
<br>end

<br>figure, subplot(2, 3, 1), imshow(A, []);
<br>subplot(2, 2, 2), imshow(B, []), title('128 gray levels');
<br>subplot(2, 2, 3), imshow(C, []), title('64 gray levels');
<br>subplot(2, 2, 4), imshow(D, []), title('32 gray levels');

<br>figure, subplot(2, 3, 1), imshow(E, []), title('16 gray levels');
<br>subplot(2, 2, 2), imshow(F, []), title('8 gray levels');
<br>subplot(2, 2, 3), imshow(G, []), title('4 gray levels');
<br>subplot(2, 2, 4), imshow(H, []), title('2 gray levels');
