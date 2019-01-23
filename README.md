# Algorithm Drill: Простые множители

## Введение
Около 300 года до Н.Э. греческий математик [Евклид][wikipedia euclid] доказал, что каждое число, большее 1, либо (1) простое, либо (2) является произведением простых. В этом задании мы собираемся написать метод, который будет возвращать простые множители данного числа.

### Математические концепции
Чтобы выполнить это задание, нам нужно ознакомиться с несколькими математическими понятиями, которые описаны ниже.

**Простые числа**  
Если мы собираемся найти простые множители числа, нам нужно определить, явялется ли число [простым][wikipedia prime numbers]. Следующие правила описывают простые числа.

- Число больше единицы (1 - не простое)
- Число делится нацело только на само себя и на 1.

Следуя этим правилам, мы можем сказать, что 2 - простое: 2 больше 1 и оно нацело делится только на 1 и на само себя. 3 тоже простое. 4 - не простое, потому что оно нацело делится на 2. Что можно сказать о 5, 6, 7?

**Множитель (делитель)**  
Мы также должны определиться с тем, что такое множитель. Число является множителем другого, если это другое число делится нацело на данное. Например, 2 - множитель 4, потому что 4 нацело делится на 2. 1 и 4 также являются делителями 4. 1, 2, 3 и 6 являются множителями шести, потому что 6 делится нацело на каждое из них.

**Разложение на простые множители**
```
4  = 2 * 2
6  = 2 * 3
8  = 2 * 2 * 2
9  = 3 * 3
10 = 2 * 5
12 = 2 * 2 * 3

...

873        = 3 * 3 * 97 
12056      = 2 * 2 * 2 * 11 * 137 
123123123  = 3 * 3 * 41 * 333667
```
*Рис 1*.  Примеры разложения на простые множители.

When we say that our method will return the prime factors of a number, what do we mean?  We need to find the set of prime numbers that multiply together to equal the original number.  The process of breaking a number down to a set of prime factors is known as [prime factorization][wikipedia integer factorization].  To illustrate, it would be like seeing the number four as the product of two times two.  Or, seeing twelve as the product of two times two times three.  (see Figure 1)


## Releases
### Release 0: Find a Number's Prime Factors
```ruby
prime_factors(6)
# => [2, 3]
prime_factors(8)
# => [2, 2, 2]
prime_factors(123123123)
# => [3, 3, 41, 333667]
```
*Figure 2*. Our method takes a number and returns its prime factors.

We'll write a `prime_factors` method that accepts one argument, a number, and returns an array of the number's prime factors.  As always, we need to document the behavior of our method through tests.  The basic behavior of our method is shown in Figure 2.  Are there any edge cases that we should cover in tests?  How should our method behave if the argument passed in is itself a prime number?


### Release 1: Refactor
Let's examine our code to see if it's the highest quality that we can write.  Are there any code smells that we can eliminate?  We want to have methods that do only one thing.  Can we extract any methods?  Maybe for determining whether or not a number is prime, or for finding possible factors of a given number?  

Do we do any rework in our method?  For example, do we check whether any number is prime more than once?  If we are making repeat calculations, can we remove them?


## Conclusion
Writing an efficient prime factorization algorithm is a problem that mathematicians and computer scientists have unsuccessfully tried to solve ... [at least for very large numbers][wikipedia rsa-768].  There was even a [contest][wikipedia rsa challenge] held to incentivize working on algorithms to find the prime factors of specific numbers.


[wikipedia euclid]: https://ru.wikipedia.org/wiki/%D0%95%D0%B2%D0%BA%D0%BB%D0%B8%D0%B4
[wikipedia integer factorization]: https://en.wikipedia.org/wiki/Integer_factorization
[wikipedia prime numbers]: https://ru.wikipedia.org/wiki/%D0%9F%D1%80%D0%BE%D1%81%D1%82%D0%BE%D0%B5_%D1%87%D0%B8%D1%81%D0%BB%D0%BE
[wikipedia rsa-768]: https://en.wikipedia.org/wiki/RSA_numbers#RSA-768
[wikipedia rsa challenge]: https://en.wikipedia.org/wiki/RSA_Factoring_Challenge


