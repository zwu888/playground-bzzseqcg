# Range-based for loop 2
```C++ runnable
template <typename DataType>
 class PodArray {
 public:
   class iterator {
   public:
     iterator(DataType * ptr): ptr(ptr){}
     iterator operator++() { ++ptr; return *this; }
     bool operator!=(const iterator & other) const { return ptr != other.ptr; }
     const DataType& operator*() const { return *ptr; }
   private:
     DataType* ptr;
   };
 private:
   unsigned len;
   DataType *val;
 public:
   iterator begin() const { return iterator(val); }
   iterator end() const { return iterator(val + len); }

   // rest of the container definition not related to the question ...
 };
