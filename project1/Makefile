# Definisanje promenljivih
CC = gcc
CFLAGS = -Wall -g
INCLUDES = -I./include

# Folder sa izvorima
SRC_DIR = source
OBJ_DIR = obj
BIN_DIR = bin

# Pravilo za build svakog fajla
# Pravilo za kompilaciju svakog .c fajla u .o fajl
$(OBJ_DIR)/%.o: $(SRC_DIR)/%.c
	@mkdir -p $(OBJ_DIR)  # Pravimo obj/ folder samo jednom
	$(CC) $(CFLAGS) $(INCLUDES) -c $< -o $@

# Pravilo za generisanje izlaznog fajla
$(BIN_DIR)/%: $(OBJ_DIR)/%.o
	@mkdir -p $(BIN_DIR)  # Pravimo bin/ folder samo jednom
	$(CC) $< -o $@

# Pravilo za kompilaciju i generisanje izvršnog fajla
# Komanda make <ime_fajla> (npr. make main)
%: $(SRC_DIR)/%.c
	$(CC) $(CFLAGS) $(INCLUDES) -o $(BIN_DIR)/$@ $<

# Pravilo za pokretanje programa
run: $(BIN_DIR)/test1
	./$(BIN_DIR)/test1

# Pravilo za čišćenje generisanih fajlova
clean:
	rm -rf $(OBJ_DIR) $(BIN_DIR)