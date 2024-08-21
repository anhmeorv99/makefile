# CC: loại biên dịch cho C, default cc
# CXX: loại biên dịch cho C++, default g++
# CFLAGS: cờ bổ sung tính năng như include thư viện ... cho C
# CXXFLAGS: cờ bổ sung tính năng như include thư viện ... cho C++
# CPPFLAGS: cung cấp cho bộ tiền xử lý C
# LDFLAGS: cung cấp các trình liên kết (linker)

DEBUG = 1
EXECUTABLE_NAME = main

CXX_STANDARD = c++17
CXX_WARNINGS = -Wall -Wextra -Wpedantic
CXX = g++
CXXFLAGS = $(CXX_WARNINGS) -std=$(CXX_STANDARD)
LDFLAGS =

ifeq ($(DEBUG), 1)
CXXFLAGS += -g -O0
else
CXXFLAGS += -O3
endif

COMPILER_CALL = $(CXX) $(CXXFLAGS)

build: my_lib.o main.o
	$(COMPILER_CALL) main.o my_lib.o $(LDFLAGS) -o $(EXECUTABLE_NAME)

main.o:
	$(COMPILER_CALL) main.cc -c

my_lib.o:
	$(COMPILER_CALL) my_lib.cc -c

execute:
	./main

clean:
	rm -f *.o
	rm -f main
