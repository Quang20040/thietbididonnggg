Bùi Văn Quang 22810310162
bai 1:
import React from 'react';
import { View, Text, FlatList, Alert, StyleSheet, TouchableOpacity } from 'react-native';

const products = [
  { id: '1', name: 'Product A', price: '10.00' },
  { id: '2', name: 'Product B', price: '15.00' },
  { id: '3', name: 'Product C', price: '20.00' },
];

const FlatListExample = () => {
  const handlePress = (productName) => {
    Alert.alert('Product Selected', `You selected: ${productName}`);
  };

  const renderItem = ({ item }) => (
    <TouchableOpacity onPress={() => handlePress(item.name)}>
      <View style={styles.item}>
        <Text style={styles.name}>{item.name}</Text>
        <Text style={styles.price}>${item.price}</Text>
      </View>
    </TouchableOpacity>
  );

  return (
    <FlatList
      data={products}
      keyExtractor={(item) => item.id}
      renderItem={renderItem}
      contentContainerStyle={styles.list}
    />
  );
};

const styles = StyleSheet.create({
  list: {
    padding: 10,
  },
  item: {
    padding: 15,
    backgroundColor: '#f9f9f9',
    marginBottom: 10,
    borderRadius: 5,
  },
  name: {
    fontSize: 16,
    fontWeight: 'bold',
  },
  price: {
    fontSize: 14,
    color: 'gray',
  },
});

export default FlatListExample;
bai2
import React from 'react';
import { View, Text, SectionList, Alert, StyleSheet, TouchableOpacity } from 'react-native';

const groupedProducts = [
  { title: 'Category A', data: ['Product A1', 'Product A2', 'Product A3'] },
  { title: 'Category B', data: ['Product B1', 'Product B2'] },
  { title: 'Category C', data: ['Product C1', 'Product C2', 'Product C3'] },
];

const SectionListExample = () => {
  const handlePress = (productName) => {
    Alert.alert('Product Selected', `You selected: ${productName}`);
  };

  const renderItem = ({ item }) => (
    <TouchableOpacity onPress={() => handlePress(item)}>
      <Text style={styles.item}>{item}</Text>
    </TouchableOpacity>
  );

  const renderSectionHeader = ({ section }) => (
    <View style={styles.header}>
      <Text style={styles.headerText}>{section.title}</Text>
    </View>
  );

  return (
    <SectionList
      sections={groupedProducts}
      keyExtractor={(item, index) => item + index}
      renderItem={renderItem}
      renderSectionHeader={renderSectionHeader}
      contentContainerStyle={styles.list}
    />
  );
};

const styles = StyleSheet.create({
  list: {
    padding: 10,
  },
  header: {
    backgroundColor: '#f1f1f1',
    padding: 10,
  },
  headerText: {
    fontSize: 16,
    fontWeight: 'bold',
  },
  item: {
    padding: 15,
    backgroundColor: '#ffffff',
    marginBottom: 5,
    borderRadius: 5,
  },
});

export default SectionListExample;
so sanh 
# FlatList vs SectionList

## Họ Tên: [Bùi Văn Quang]  
## Mã Sinh Viên: [22810310162]  

---

### **1. Mục đích sử dụng**
- **FlatList**: Hiển thị danh sách phẳng, không phân nhóm.
- **SectionList**: Hiển thị danh sách được phân thành các nhóm (sections).

### **2. Cấu trúc dữ liệu**
- **FlatList**: Nhận một mảng các đối tượng.
- **SectionList**: Nhận một mảng các đối tượng có thuộc tính `title` (header của nhóm) và `data` (danh sách các mục trong nhóm).

### **3. Hiệu năng**
- Cả hai đều tối ưu hóa hiển thị dữ liệu lớn bằng cách tải từng phần (virtualized list).
- **SectionList** có thêm chi phí khi xử lý cấu trúc phân nhóm.

### **4. Tính dễ sử dụng**
- **FlatList**: Đơn giản, dễ sử dụng khi không cần nhóm dữ liệu.
- **SectionList**: Phức tạp hơn nhưng cần thiết khi hiển thị dữ liệu phân nhóm.

---

## Hướng dẫn chạy ứng dụng:
1. Clone repository từ link git.
2. Cài đặt dependencies: `npm install`.
3. Chạy ứng dụng: `npx react-native run-android` hoặc `npx react-native run-ios`.
