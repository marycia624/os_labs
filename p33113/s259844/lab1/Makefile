
CC = gcc
LD = gcc
CFLAGS = -pedantic-errors -Wall -Werror -g -O0 # -O2
LDFLAGS = -pthread

BUILDPATH = build
SOURCES = lab1.c thread_pool.c
HEADERS = thread_pool.h
TARGET = lab1

OBJECTS = $(SOURCES:%.c=$(BUILDPATH)/%.o)

.PHONY: all build clean cltmp
.SUFFIXES:

all: build

cltmp:
	@rm -v ?????????.?.bin 2> /dev/null ; true

clean: cltmp
	@rm -vrf $(BUILDPATH) 2> /dev/null ; true
	@rm -v $(TARGET) 2> /dev/null ; true

build: $(TARGET)

%.c:

$(OBJECTS): $(BUILDPATH)/%.o : %.c $(HEADERS)
	@mkdir -p $(@D)
	$(CC) -c -o $@ $< $(CFLAGS)

$(TARGET): $(OBJECTS)
	$(LD) -o $@ $^ $(LDFLAGS)
