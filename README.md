<img width="1232" height="384" alt="image" src="https://github.com/user-attachments/assets/1ee85638-e957-4474-bfa6-255812f469f7" /><img width="1232" height="384" alt="image" src="https://github.com/user-attachments/assets/d25568af-8237-4354-95ff-8bbc8439a971" />ТЕМА 1

ЗАДАНИЕ 1                                                                                                            void main() {
 
  print(convertCurrency(10000, 90.5)); 
  print(convertCurrency(5000, 92.25)); 
  print(convertCurrency(100, 0)); 
}

String convertCurrency(int rubles, double usdRate) {
  if (usdRate <= 0) {
    return "Ошибка: неверный курс";
  }
  
  double dollars = rubles / usdRate;
  
  return dollars.toStringAsFixed(2);
}
<img width="1600" height="772" alt="image" src="https://github.com/user-attachments/assets/bcbc15b6-f3a4-42a5-a29a-6e001420244e" />


ЗАДАНИЕ 2 void main() {
  // Примеры использования
  print(parseAge("25"));
  print(parseAge(" 30 ")); 
  print(parseAge("двадцать пять"));
  print(parseAge("-5")); 
}


int parseAge(String input) {
 
  int? age = int.tryParse(input.trim());
  
  return age ?? -1; 
}
<img width="1632" height="612" alt="image" src="https://github.com/user-attachments/assets/d5c09b6a-d65f-4d55-a9f2-e996d71c1eee" />


ЗАДАНИЕ 3-5                                                                                                          void main() {
  
  print(calculateDp(100, 2.75)); 
  print(calculateDp(50, 1.0)); 
  print(calculateDp(10, 0)); 
}


double calculateDp(double px, double density) {
  if (density == 0) {
    return 0.0; 
  }
  return px / density;
}
<img width="1660" height="636" alt="image" src="https://github.com/user-attachments/assets/15f0a433-e323-4678-a4cf-d5e0854a381a" />


Тема 2. Строки (String), интерполяция и кодовые точки (Runes)

ЗАДАНИЕ 1 String maskEmail(String email) {
  final parts = email.split('@');
  if (parts.length != 2) return email;
  
  final name = parts[0];
  final domain = parts[1];
  
  if (name.length <= 2) return email;
  
  final firstChar = name[0];
  final lastChar = name[name.length - 1];
  final stars = '*' * (name.length - 2);
  
  return '$firstChar$stars$lastChar@$domain';
}

void main() {
  print(maskEmail('ivanov.flutter@gmail.com'));
}
<img width="1228" height="468" alt="image" src="https://github.com/user-attachments/assets/bc48e291-63ab-430d-8afe-19429c2d1c9f" />


ЗАДАНИЕ 2 bool isSecureLink(String url) {
  return url.startsWith('https://');
}

void main() {
  print(isSecureLink('https://dart.dev'));
  print(isSecureLink('http://dart.dev'));
}
<img width="1256" height="496" alt="image" src="https://github.com/user-attachments/assets/5b6535dd-24de-44a9-a401-a1edb6d36fee" />


Задание 3 String getInitials(String fullName) {
  final words = fullName.trim().split(RegExp(r'\s+'));
  if (words.length < 2) return '';
  
  return words[0][0].toUpperCase() + words[1][0].toUpperCase();
}

void main() {
  print(getInitials('Александр Пушкин'));
}
<img width="1276" height="440" alt="image" src="https://github.com/user-attachments/assets/41a8b3d6-5096-4e49-ab6e-1d2a5e0c59d8" />


задание 4 Map<String, dynamic> parseCartItem(String csv) {
  final parts = csv.split(',');
  
  return {
    'name': parts[0],
    'quantity': int.tryParse(parts[1]) ?? 0,
    'price': double.tryParse(parts[2]) ?? 0.0,
  };
}

void main() {
  final item = parseCartItem('Яблоко,3,150.5');
  print('Наименование: ${item['name']}');
  print('Количество: ${item['quantity']}');
  print('Стоимость: ${item['price']}');
}
<img width="1200" height="448" alt="image" src="https://github.com/user-attachments/assets/038ba1c9-e000-4d93-8647-58fb5dfe4d7f" />


задание 5 int getRealLength(String text) {
  return text.runes.length;
}

void main() {
  const textWithEmoji = 'Привет 👨‍👩‍👧‍👦!';
  print(getRealLength(textWithEmoji));
}
<img width="1256" height="440" alt="image" src="https://github.com/user-attachments/assets/98821757-6998-4b4d-8fdc-37ebe1fb3f9d" />


Тема 3. Логический тип (bool) и строгость условий

ЗАДАНИЕ 1 bool checkScreenAccess({
  required bool isAuthorized,
  required bool isEmailConfirmed,
  required bool isBlocked,
}) {
  return isAuthorized && isEmailConfirmed && !isBlocked;
}

void main() {
  print(checkScreenAccess(isAuthorized: true, isEmailConfirmed: true, isBlocked: false));
}
<img width="1224" height="404" alt="image" src="https://github.com/user-attachments/assets/a5a31496-5028-4cdc-b2f4-2bebaaa3b99d" />


Задание 2 bool isBlank(String? input) {
  return input == null || input.trim().isEmpty;
}

void main() {
  print(isBlank(null));
  print(isBlank(''));
  print(isBlank(' '));
  print(isBlank('Текст'));
}
<img width="1268" height="464" alt="image" src="https://github.com/user-attachments/assets/0ec969dc-ec8c-42fb-8d5b-313203e51911" />


задание 3 bool toggleDarkMode(bool isDarkMode) {
  return !isDarkMode;
}

void main() {
  bool currentTheme = false;
  currentTheme = toggleDarkMode(currentTheme);
  print(currentTheme);
}
<img width="1204" height="416" alt="image" src="https://github.com/user-attachments/assets/d2014c32-bf5b-44f9-821d-62322f8d7095" />



задание 4-5 bool canRentCar(int age, int drivingExperience) {
  return age >= 21 && drivingExperience >= 2;
}

void main() {
  print(canRentCar(25, 3));
  print(canRentCar(20, 3));
  print(canRentCar(25, 1));
}
<img width="1264" height="484" alt="image" src="https://github.com/user-attachments/assets/5a12374d-820a-4dd5-8e5a-2f02efc05705" />



Тема 4. Списки (List): списковые включения и spread-операторы

задание 1 List<int> removeDuplicates(List<int> list) {
  return list.toSet().toList();
}

void main() {
  final numbers = [1, 2, 2, 3, 1, 4, 5, 5];
  print(removeDuplicates(numbers));
}
<img width="1208" height="520" alt="image" src="https://github.com/user-attachments/assets/4da07187-11e7-422f-a84d-1361fa3be7e9" />


задание 2 List<T> getPage<T>(List<T> list, int page, int pageSize) {
  final start = (page - 1) * pageSize;
  
  if (start < 0 || start >= list.length) {
    return [];
  }
  
  final end = (start + pageSize < list.length) ? start + pageSize : list.length;
  
  return list.sublist(start, end);
}

void main() {
  final list = ['A', 'B', 'C', 'D', 'E', 'F', 'G'];
  print(getPage(list, 2, 3));
}
<img width="1160" height="424" alt="image" src="https://github.com/user-attachments/assets/52393da0-1499-48ed-8f82-890205281020" />


задание 3 void main() {
  final prices = [150.5, 20.0, 300.99, 45.0];
  
  prices.sort((a, b) => b.compareTo(a));
  
  print(prices);
}
<img width="1204" height="436" alt="image" src="https://github.com/user-attachments/assets/a219e0b4-2785-44d8-8f01-f7034178eed6" />


задание 4 
String findLongWordClean(List<String> words) {
  return words.firstWhere(
    (word) => word.length > 8,
    orElse: () => 'Не найдено',
  );
}

void main() {
  final words = ['яблоко', 'апельсин', 'виноград', 'мандарин'];
  print(findLongWordClean(words));
}
<img width="1228" height="412" alt="image" src="https://github.com/user-attachments/assets/6c92f307-369a-49fb-a04d-dcb58cfc25bd" />


задание 5 List<String> generateSlots() {
  return List.generate(10, (index) => 'Слот ${index + 1}');
}

void main() {
  final slots = generateSlots();
  print(slots);
}
<img width="1248" height="436" alt="image" src="https://github.com/user-attachments/assets/af2c5fa8-1c29-4302-9d96-4a367517d7ac" />


Тема 5. Множества (Set) и Словари (Map): парсинг JSON-структур


задание 1 Map<String, int> countWordFrequency(String text) {
  final words = text.toLowerCase().split(RegExp(r'\s+'));
  final frequencyMap = <String, int>{};

  for (var word in words) {
    if (word.isNotEmpty) {
      frequencyMap[word] = (frequencyMap[word] ?? 0) + 1;
    }
  }

  return frequencyMap;
}

void main() {
  const text = 'яблоко банан яблоко апельсин банан яблоко';
  print(countWordFrequency(text));
}
<img width="1256" height="384" alt="image" src="https://github.com/user-attachments/assets/b98722a1-e5f8-453c-8067-399fbbab8cc8" />


задание 2 Set<String> symmetricDifference(Set<String> set1, Set<String> set2) {
  final diff1 = set1.difference(set2);
  final diff2 = set2.difference(set1);
  return diff1.union(diff2);
}

void main() {
  final setA = {'flutter', 'dart', 'android'};
  final setB = {'dart', 'ios', 'swift'};
  
  print(symmetricDifference(setA, setB));
}
<img width="1268" height="408" alt="image" src="https://github.com/user-attachments/assets/f3e74e22-5bd8-4bce-a3f0-67c46589923b" />


задание 3-5 String getStringSetting(Map<String, dynamic> settings, String key, {String defaultValue = ''}) {
  final value = settings[key];
  if (value is String) {
    return value;
  }
  return defaultValue;
}

void main() {
  final Map<String, dynamic> config = {
    'appName': 'MyApp',
    'version': 1.0,
    'isDebug': true,
  };

  print(getStringSetting(config, 'appName', defaultValue: 'Unknown'));
  print(getStringSetting(config, 'version', defaultValue: '1.0.0'));
  print(getStringSetting(config, 'missingKey', defaultValue: 'Default'));
} Map<String, double> convertToDollars(Map<String, double> rubles, double usdRate) {
  return rubles.map((key, value) => MapEntry(key, value / usdRate));
}

void main() {
  final pricesInRubles = {
    'Хлеб': 50.0,
    'Молоко': 80.0,
    'Сыр': 400.0,
  };
  
  final pricesInDollars = convertToDollars(pricesInRubles, 90.0);
  print(pricesInDollars);
}Map<String, List<Map<String, dynamic>>> groupUsersByCity(List<Map<String, dynamic>> users) {
  final groupedUsers = <String, List<Map<String, dynamic>>>{};

  for (final user in users) {
    final city = user['city'] as String? ?? 'Неизвестно';
    
    if (!groupedUsers.containsKey(city)) {
      groupedUsers[city] = [];
    }
    
    groupedUsers[city]!.add(user);
  }

  return groupedUsers;
}

void main() {
  final users = [
    {'name': 'Иван', 'city': 'Москва'},
    {'name': 'Анна', 'city': 'Санкт-Петербург'},
    {'name': 'Олег', 'city': 'Москва'},
    {'name': 'Мария', 'city': 'Казань'},
  ];

  final result = groupUsersByCity(users);
  print(result);
}
<img width="1256" height="424" alt="image" src="https://github.com/user-attachments/assets/e10d9769-f603-4413-af64-c1acf9f7c02c" />


Тема 6. Null Safety, Records (кортежи) и Pattern Matching


задание 1 (double x, double y) getScreenCenter(double screenWidth, double screenHeight) {
  return (screenWidth / 2, screenHeight / 2);
}

void main() {
  final center = getScreenCenter(1080.0, 2400.0);
  print(center);
}
<img width="1256" height="424" alt="image" src="https://github.com/user-attachments/assets/281533ce-f873-42e5-80ff-28f7eb88289e" />


задание 2 void main() {
  String? bio; // Может быть null или содержать текст
  
  String displayBio = bio ?? 'Информация отсутствует';
  
  print(displayBio);
}
<img width="1236" height="424" alt="image" src="https://github.com/user-attachments/assets/ab399b59-0de3-4179-b9b8-77237a911a7e" />



задание 3 void checkJsonFormat(Map<String, dynamic> json) {
  switch (json) {
    case {'id': var id}:
      print('Валидный объект с id: $id');
    case {'error': var errorMessage}:
      print('Объект с ошибкой: $errorMessage');
    default:
      print('Неизвестный формат пакета');
  }
}

void main() {
  checkJsonFormat({'id': 1, 'name': 'Ivan'});
  checkJsonFormat({'error': 'Not Found'});
  checkJsonFormat({'status': 'ok'});
}
<img width="1236" height="424" alt="image" src="https://github.com/user-attachments/assets/cda79964-e073-4912-a70f-1a55961249c1" />



задание 4 late final double expensiveCalculation = calculateSomething();

double calculateSomething() {
  print('Выполнение сложных вычислений...');
  return 3.14159;
}

void main() {
  print('Программа запущена');
  print('Переменная еще не вычислена');
  
  // Первое обращение - запускается вычисление
  print('Результат: $expensiveCalculation');
  
  // Второе обращение - берется готовое значение
  print('Результат снова: $expensiveCalculation');
}
<img width="1244" height="404" alt="image" src="https://github.com/user-attachments/assets/399a03e9-abb9-4636-85c4-7f36ecfd8c36" />


задание 5 void main() {
  List<int>? numbers = [10, 20, 30];
  // List<int>? numbers = null; // Для проверки случая с null
  
  int firstElement = numbers?[0] ?? -1;
  
  print(firstElement);
}
<img width="1232" height="384" alt="image" src="https://github.com/user-attachments/assets/164fe167-2f47-43ab-a870-e14054d1f1a2" />


50 Смешанных заданий по обработке данных


задание 1 double calculateTotalCost(double price) {
  double discount = price * 0.15;
  if (discount > 500) {
    discount = 500;
  }
  return price - discount;
}

void main() {
  print(calculateTotalCost(1000)); // 850.0
  print(calculateTotalCost(5000)); // 4500.0
}
<img width="1260" height="452" alt="image" src="https://github.com/user-attachments/assets/17863dcc-d4e0-4553-ad77-f5265ad142c0" />


задание 2 String formatPrice(double price) {
  final parts = price.toStringAsFixed(2).split('.');
  final integerPart = parts[0];
  final decimalPart = parts[1];
  
  final buffer = StringBuffer();
  int count = 0;
  
  for (int i = integerPart.length - 1; i >= 0; i--) {
    buffer.write(integerPart[i]);
    count++;
    if (count == 3 && i != 0) {
      buffer.write(' ');
      count = 0;
    }
  }
  
  final formattedInteger = buffer.toString().split('').reversed.join('');
  return '$formattedInteger.$decimalPart ₽';
}

void main() {
  print(formatPrice(15400900.5)); // 15 400 900.50 ₽
}
<img width="1192" height="436" alt="image" src="https://github.com/user-attachments/assets/a07f8688-86aa-49ad-95c9-b665546d9df7" />


задание 3 int calculateCashback(double checkAmount) {
  return checkAmount ~/ 100;
}

void main() {
  print(calculateCashback(350)); // 3
  print(calculateCashback(99)); // 0
}
<img width="1184" height="384" alt="image" src="https://github.com/user-attachments/assets/caffc714-8bcf-48e3-b109-ae2fec9ca093" />


задание 4 double clampVolume(double volume) {
  return volume.clamp(0.0, 1.0);
}

void main() {
  print(clampVolume(-0.5)); // 0.0
  print(clampVolume(0.5)); // 0.5
  print(clampVolume(1.5)); // 1.0
}
<img width="1236" height="488" alt="image" src="https://github.com/user-attachments/assets/a1f39fb4-fca6-45ae-b90c-8989082315c5" />


задание 5 double convertBytesToMb(int bytes) {
  final mb = bytes / (1024 * 1024);
  return double.parse(mb.toStringAsFixed(1));
}

void main() {
  print(convertBytesToMb(1572864)); // 1.5
  print(convertBytesToMb(5000000)); // 4.8
}
![Uploading image.png…]()




задание 6 double calculateProgress(int current, int total) {
  if (total <= 0) return 0.0;
  return (current / total).clamp(0.0, 1.0);
}

void main() {
  print(calculateProgress(5, 10)); // 0.5
  print(calculateProgress(15, 10)); // 1.0
}
![Uploading image.png…]()


задание 7 int roundUpToNearestTen(int number) {
  return ((number + 9) ~/ 10) * 10;
}

void main() {
  print(roundUpToNearestTen(43)); // 50
  print(roundUpToNearestTen(40)); // 40
  print(roundUpToNearestTen(41)); // 50
}
![Uploading image.png…]()
