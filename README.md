7. 主菜单
最后，我们定义一个主菜单函数，让用户可以选择执行不同的操作。

python
def main_menu():
    while True:
        print("\nShirt Management Software")
        print("1. Add Shirt")
        print("2. List Shirts")
        print("3. Find Shirt by ID")
        print("4. Update Shirt")
        print("5. Delete Shirt")
        print("6. Exit")
        
        choice = input("Enter your choice: ")
        
        if choice == '1':
            shirt_id = input("Enter shirt ID: ")
            brand = input("Enter brand: ")
            size = input("Enter size: ")
            quantity = int(input("Enter quantity: "))
            add_shirt(shirt_id, brand, size, quantity)
        elif choice == '2':
            list_shirts()
        elif choice == '3':
            shirt_id = input("Enter shirt ID to find: ")
            find_shirt(shirt_id)
        elif choice == '4':
            shirt_id = input("Enter shirt ID to update: ")
            new_brand = input("Enter new brand (leave blank to keep current): ") or None
            new_size = input("Enter new size (leave blank to keep current): ") or None
            new_quantity = input("Enter new quantity (leave blank to keep current): ")
            if new_quantity:
                new_quantity = int(new_quantity)
            else:
                new_quantity = None
            
            new_data = {}
            if new_brand:
                new_data['brand'] = new_brand
            if new_size:
                new_data['size'] = new_size
            if new_quantity is not None:
                new_data['quantity'] = new_quantity
            
            update_shirt(shirt_id, new_data)
        elif choice == '5':
            shirt_id = input("Enter shirt ID to delete: ")
            delete_shirt(shirt_id)
        elif choice == '6':
            print("Exiting the software.")
            break
        else:
            print("Invalid choice. Please try again.")
 
if __name__ == "__main__":
    main_menu()
8. 运行程序
将上述代码保存为一个Python文件（例如shirt_management.py），然后在终端或命令行中运行该文件：

bash
python shirt_management.py
你将看到一个简单的文本菜单，允许你添加、查询、更新和删除衬衣库存。
