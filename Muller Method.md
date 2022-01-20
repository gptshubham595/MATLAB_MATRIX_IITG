f=@(x)x^3+x^2-4*x-4;
function mullers(func,x)
xold=100;
while (abs(x(3)-xold)/x(3))*100>1e-3
    %disp(x)
    f=eval(func2str(func));
    A=[(x(1)-x(3))^2 x(1)-x(3);(x(2)-x(3))^2 x(2)-x(3)];
    B=[f(3)-f(1) f(3)-f(2)]';
    l=inv(A)*B;f(3)];
    sl=sqrt(l(2)^2-4*l(1)*l(3));
    xu=x(3)+(-l(2) + sign(l(2)*sl)/(2*l(1)));
    xc=abs(x-xu);
    xs=sortrows([xc' x'],1);
    xold=xs(3,2);
    x=[xs(1:2,2);xu]';
end
disp("FINAL ANS");
disp(x(3));

%disp([ x(3) abs((x(3)-xold)/x(3))*100]);
