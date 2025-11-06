# CommandProjectPV-425  
**Система измерения производительности параллельных алгоритмов на платформе .NET**

> Курсовой проект группы ПВ-425 по дисциплине «Программирование на платформе .NET»

![.NET](https://img.shields.io/badge/.NET-9.0-blue)
![WPF](https://img.shields.io/badge/UI-WPF-purple)
![MVVM + DI](https://img.shields.io/badge/Architecture-MVVM%20%2B%20DI-green)
![SQLite](https://img.shields.io/badge/Database-SQLite-lightgrey)

---

## 📄 Оглавление

- [Описание проекта](#-описание-проекта)
- [Структура проекта](#-структура-проекта)
- [Структура базы данных](#-структура-базы-данных-benchmarkresults)
- [Архитектура и технологии](#-архитектура-и-технологии)
- [Команда разработчиков](#-команда-разработчиков)
- [Скриншоты (пример)](#-скриншоты-пример)
- [Важные файлы](#-важные-файлы)
- [Лицензия](#-лицензия)

---

## 📌 Описание проекта

WPF-приложение для объективного сравнения производительности **9 методов выполнения** (от последовательного цикла `for` до SIMD-инструкций) при решении **5 вычислительных задач** на массивах.  

- Измерения проводятся с помощью **BenchmarkDotNet**.  
- Результаты визуализируются в виде **интерактивных графиков**.  
- Данные сохраняются в локальную **базу данных SQLite** и могут экспортироваться в **JSON**.  
- Архитектура: **MVVM + Dependency Injection + Entity Framework Core**.

---

## 🗃 Структура проекта

CommandProjectPV-425/
├── Helpers/
│   └── Вспомогательные классы (JsonHelper, SystemInfoProvider)
├── Interfaces/
│   ├── IBenchmarkService.cs
│   ├── IChartService.cs
│   └── IDataService.cs
├── Models/
│   ├── BenchmarkResult.cs
│   └── AppDbContext.cs
├── Services/
│   ├── BenchmarkService.cs
│   ├── ChartService.cs
│   └── DataService.cs
├── Tests/
│   ├── CountAboveAverage.cs
│   ├── DivisibleThreeOrFive.cs
│   ├── FindPrimeNumbers.cs
│   ├── MaxFrequencyOfElements.cs
│   └── MaximumOfNonExtremeElements.cs
├── ViewModels/
│   ├── MainViewModel.cs
│   └── ChartViewModel.cs
├── Views/
│   ├── MainWindow.xaml
│   ├── ChartView.xaml
│   └── ResultRowTemplate.xaml
├── App.xaml
├── App.xaml.cs
└── bin/Release/net9.0-windows/Data/benchmark.db ← автоматически создаётся при первом запуске
