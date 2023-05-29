class KeyValueNode:
    def __init__(self, key, value):
        self.key = key
        self.value = value
        self.next = None


class ChainingDictionaryWithReplacement:
    def __init__(self, size):
        self.size = size
        self.hash_table = [None] * size

    def hash_function(self, key):
        return hash(key) % self.size

    def insert(self, key, value):
        index = self.hash_function(key)
        node = self.hash_table[index]

        while node is not None:
            if node.key == key:
                node.value = value
                return
            node = node.next

        new_node = KeyValueNode(key, value)
        new_node.next = self.hash_table[index]
        self.hash_table[index] = new_node

    def display(self):
        for index in range(self.size):
            node = self.hash_table[index]
            while node is not None:
                print(f"Key: {node.key}, Value: {node.value}")
                node = node.next


class ChainingDictionaryWithoutReplacement:
    def __init__(self, size):
        self.size = size
        self.hash_table = [None] * size

    def hash_function(self, key):
        return hash(key) % self.size

    def insert(self, key, value):
        index = self.hash_function(key)

        if self.hash_table[index] is None:
            self.hash_table[index] = KeyValueNode(key, value)
        else:
            current_node = self.hash_table[index]
            while current_node.next is not None:
                current_node = current_node.next
            current_node.next = KeyValueNode(key, value)

    def display(self):
        for index in range(self.size):
            node = self.hash_table[index]
            while node is not None:
                print(f"Key: {node.key}, Value: {node.value}")
                node = node.next


# Testing the ChainingDictionary classes
print("Chaining with Replacement:")
dictionary_with_replacement = ChainingDictionaryWithReplacement(10)

dictionary_with_replacement.insert("apple", 5)
dictionary_with_replacement.insert("banana", 7)
dictionary_with_replacement.insert("cherry", 10)
dictionary_with_replacement.insert("date", 12)
dictionary_with_replacement.insert("banana", 8)  # Replacing value for existing key

dictionary_with_replacement.display()

print("---------------------------------------------------")

print("\nChaining without Replacement:")
dictionary_without_replacement = ChainingDictionaryWithoutReplacement(10)

dictionary_without_replacement.insert("apple", 5)
dictionary_without_replacement.insert("banana", 7)
dictionary_without_replacement.insert("cherry", 10)
dictionary_without_replacement.insert("date", 12)

dictionary_without_replacement.display()
