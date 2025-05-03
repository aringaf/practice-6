#include <stdio.h>
#include <string.h>

int main() {
    // Максимальное количество строк и их длина
    #define MAX_LINES 100
    #define MAX_LINE_LENGTH 200
    
char lines[MAX_LINES][MAX_LINE_LENGTH];
    int line_count = 0;    
    // Чтение ввода (симулируем ввод)
    strcpy(lines[0], "/test.txt");
    strcpy(lines[1], "Привет");
    strcpy(lines[2], "Мир");
    line_count = 3;
    
// Выводим имя файла (первая строка)
    printf("Имя файла: %s\n", lines[0]);
    
// Объединяем строки содержимого (со второй строки до конца)
    char content[MAX_LINES * MAX_LINE_LENGTH] = ""; // Буфер для содержимого
    
for (int i = 1; i < line_count; i++) {
        strcat(content, lines[i]);
        if (i != line_count - 1) {
            strcat(content, "\n"); // Добавляем перенос строки, кроме последней строки
        }
    }
    
 // Выводим содержимое файла
    printf("\nСодержимое файла:\n%s\n", content);
    
 // Проверяем наличие слова "Привет" в содержимом
    char target[] = "Привет";
    char *result = strstr(content, target);
    
if (result != NULL) {
        printf("\nСлово \"%s\" найдено в тексте\n", target);
    } else {
        printf("\nСлово \"%s\" не найдено\n", target);
    }
    
  return 0;
}
