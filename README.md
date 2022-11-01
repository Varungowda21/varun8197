# varun8197
Here they are 5 options,where you can add product name and cost ,and you can search and remove product name and cost and view them in pie chart and we can exit out of the loop.
import matplotlib.pyplot as plt
product=[]
cost=[]
while True:
    print("1:add product")
    print("2:search product")
    print("3:remove product")
    print("4:view")
    print("5:exit")
    n=int(input())
    if n==1:
        name=input("Enter product name:")
        price=eval(input("Enter the product price:"))
        product.append(name)
        cost.append(price)
    elif n==2:
        product_name=input("Enter product name:")
        if product_name in product:
            idx=product.index(product_name)
            print("{0} price {1}/rs".format(product_name,cost[idx]))
        else:
            print("not found")
    elif n==3:
        product_name=input("Enter the product name to remove:")
        if product_name in product:
            idx=product.index(product_name)
            cost.pop(idx)
            product.pop(idx)
        else:
            print("not found")
    elif n==4:
        plt.pie(cost,labels=product)
        plt.legend(title="View of products")
        plt.show()
    elif n==5:
        break
