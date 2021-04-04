# স্ট্রিং অপারেশনস \(String Operations\)

### CONCAT

যে ক্রম অনুসারে দেয়া হবে, সেভাবেই যুক্ত করবে।

```sql
CONCAT (column_1, ' ', column_4);
```

### CONCAT\_WS

যে columnগুলো উল্লেখ করে দেয়া হবে, সেগুলোকে সবার শুরুতে দেয়া চিহ্ন দিয়ে যুক্ত করবে।

```sql
CONCAT_WS(' ', column1, column2, column3, column_4);
```

### SUBSTRING

```sql
SUBSTRING(column_name_or_string, start, end);
```

এখানে ১ থেকে শুরু হবে।

```sql
SUBSTRING(column_name, -count);
```

শেষ থেকে শুরু হয়ে count সংখ্যক অক্ষর পর্যন্ত সাবস্ট্রিং দিবে।

### REPLACE

```sql
REPLACE(column_name, substring, string_to_put_in);
```

### CHAR\_LENGTH

কতগুলো অক্ষর আছে তা বলে দিবে।

```sql
CHAR_LENGTH(column_name_or_some_string);
```

### UPPER/LOWER

```sql
UPPER(some_string_or_column);
LOWER(some_string_or_column);
```

### REVERSE

```sql
REVERSE(some_string_or_column);
```

