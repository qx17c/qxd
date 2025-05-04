 self.inserted_money += coin
        print(f"已投入: ¥{coin:.1f} (总计: ¥{self.inserted_money:.1f})")
        return True
    
    def select_product(self, choice):
        """选择商品"""
        if choice < 1 or choice > len(self.products):
            print("错误: 无效的选择")
            return False
        
        product_name = list(self.products.keys())[choice - 1]
        product_info = self.products[product_name]
        
        if product_info["stock"] <= 0:
            print(f"错误: {product_name} 已售罄")
            return False
        
