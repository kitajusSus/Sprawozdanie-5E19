import numpy as np
import matplotlib.pyplot as plt

# Dane wejściowe: czasy ładowania kondensatora w sekundach
t1 = np.array([194.1, 189.5, 196.3, 204.5, 193.2, 188.6, 203.5, 213.7, 203.5])  # Czasy ładowania [s]

# Stałe układu
R = 8.2e6  # Rezystancja [Ohm]
C = 3.82e-6  # Pojemność [F]
U_inf = 300  # Napięcie końcowe (napięcie źródła) [V]

# Obliczanie średniego czasu ładowania oraz niepewności
mean_time = np.mean(t1)  # Średni czas ładowania [s]
std_dev_time = np.std(t1)  # Odchylenie standardowe (jako niepewność) [s]

# Generowanie osi czasu (1000 punktów równomiernie rozmieszczonych w zakresie od 0 do średniego czasu)
time_avg = np.linspace(0, mean_time, 1000)  # Zakres czasu [s]

# Obliczanie wartości napięcia U(t) dla średniego czasu ładowania
# Wzór: U(t) = U_inf * (1 - exp(-t / (R * C)))
U_t_avg = U_inf * (1 - np.exp(-time_avg / (R * C)))

# Tworzenie wykresu
plt.figure(figsize=(10, 6))  # Ustawienia rozmiaru wykresu

# Wykres U(t) jako funkcji czasu
plt.plot(time_avg, U_t_avg, label=f"Średni czas ładowania (t = {mean_time:.2f} s, $\sigma$ = {std_dev_time:.2f} s)", color='blue')

# Dodanie obszaru niepewności wokół krzywej (± odchylenie standardowe)
plt.fill_between(time_avg, U_t_avg - std_dev_time, U_t_avg + std_dev_time, color='blue', alpha=0.2, label='Niepewność ($\sigma$)')

# Ustawienia osi i tytułu wykresu
plt.xlabel("Czas [s]")  # Etykieta osi X
plt.ylabel("Napięcie [V]")  # Etykieta osi Y
plt.title("Zależność U(t) dla średniego czasu ładowania kondensatora")  # Tytuł wykresu

# Legenda i siatka
plt.legend()  # Dodanie legendy
plt.grid()  # Włączenie siatki

# Wyświetlenie wykresu
plt.show()
