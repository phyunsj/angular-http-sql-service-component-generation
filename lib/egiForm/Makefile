
include ./../../appweb-2.4.4/buildConfig.make
#include ./../../appweb-2.4.4/build/make/make.gcc

CXX = g++

LIB = ../libegiForm.so

SRCS =  Portfolio.cpp PortfolioHelper.cpp Stock.cpp StockHelper.cpp Company.cpp CompanyHelper.cpp myEgiForm.cpp 

OBJS = $(SRCS:.cpp=.o)

CFLAGS += -O0 -g -D_DEBUG -Wall -Wno-write-strings -Wno-write-strings  -DLINUX -D_REENTRANT -fno-stack-protector -DAMD64  -fno-exceptions -fno-rtti -fPIC -DPIC  
CFLAGS += -I. -I./../jsoncpp  -I./../sqlite-3.22
CFLAGS += -I./../../appweb-2.4.4 -I./../../appweb-2.4.4/appweb -I./../../appweb-2.4.4/mpr -I./../../appweb-2.4.4/esp -I./../../appweb-2.4.4/ejs -I./../../appweb-2.4.4/http -I./../../appweb-2.4.4/http/modules

%.o: %.cpp
	$(CXX) $(CFLAGS)  -c $<

$(LIB): $(OBJS)
	$(CXX) -shared $(OBJS) -o $(LIB)

clean:
	-@$(RM) $(OBJS)
	-@$(RM) $(LIB)

