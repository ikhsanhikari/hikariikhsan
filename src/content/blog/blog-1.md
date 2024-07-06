---
title: "Yang Perlu Kamu Tahu Tentang Spring WebFlux"
description: "Panduan Dasar Spring WebFlux dalam Bahasa Indonesia"
image: "/images/blog-1.jpg"
date: 2022-04-04T05:00:00Z
draft: false
---
Spring WebFlux adalah framework reaktif untuk membangun aplikasi web non-blocking di atas platform Spring. Cocok untuk aplikasi yang membutuhkan skalabilitas tinggi, seperti aplikasi real-time atau layanan mikro (microservices). Di artikel ini, kita akan membahas dasar-dasar Spring WebFlux dengan contoh kode yang mudah dipahami oleh pemula.

Mengapa Menggunakan Spring WebFlux?
Spring WebFlux menawarkan berbagai keuntungan, seperti:

Non-blocking I/O, yang memungkinkan aplikasi menangani lebih banyak permintaan dengan sumber daya yang sama.
Dukungan penuh untuk reaktif programming, memanfaatkan Project Reactor.
Integrasi mudah dengan ekosistem Spring lainnya.
Memulai dengan Spring WebFlux
Untuk memulai, kita akan membuat aplikasi sederhana menggunakan Spring Boot dan Spring WebFlux. Berikut adalah langkah-langkahnya:

1. Persiapan Proyek
Buat proyek Spring Boot baru dengan dependensi spring-boot-starter-webflux. Kamu bisa menggunakan Spring Initializr atau menambahkan dependensi langsung di build.gradle atau pom.xml.

plugins {
    id 'org.springframework.boot' version '2.6.4'
    id 'io.spring.dependency-management' version '1.0.11.RELEASE'
    id 'java'
}
```
group = 'com.example'
version = '0.0.1-SNAPSHOT'
sourceCompatibility = '11'

repositories {
    mavenCentral()
}

dependencies {
    implementation 'org.springframework.boot:spring-boot-starter-webflux'
    testImplementation 'org.springframework.boot:spring-boot-starter-test'
}
```

pom.xml
```
<dependencies>
    <dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-webflux</artifactId>
    </dependency>
    <dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-test</artifactId>
        <scope>test</scope>
    </dependency>
</dependencies>
```

2. Membuat Controller
Selanjutnya, kita akan membuat controller sederhana untuk menangani permintaan HTTP.

```
package com.example.demo;

import org.springframework.web.bind.annotation.GetMapping;
import org.springframework.web.bind.annotation.RestController;
import reactor.core.publisher.Mono;

@RestController
public class HelloController {

    @GetMapping("/hello")
    public Mono<String> sayHello() {
        return Mono.just("Hello, Spring WebFlux!");
    }
}
```
Controller di atas akan menangani permintaan GET ke endpoint /hello dan mengembalikan Mono<String>, yang merupakan tipe reaktif yang mewakili satu nilai atau error.

3. Menjalankan Aplikasi
Sekarang, jalankan aplikasi Spring Boot dengan menjalankan kelas utama:

```
package com.example.demo;

import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;

@SpringBootApplication
public class DemoApplication {

    public static void main(String[] args) {
        SpringApplication.run(DemoApplication.class, args);
    }
}
```

Buka browser dan akses http://localhost:8080/hello. Kamu akan melihat pesan "Hello, Spring WebFlux!".

Kesimpulan
Spring WebFlux adalah framework yang powerful untuk membangun aplikasi web reaktif. Dengan pemahaman dasar ini, kamu sudah bisa mulai mengeksplorasi fitur-fitur lanjutan lainnya. Selamat mencoba dan semoga sukses!

Jika ada pertanyaan atau butuh bantuan lebih lanjut, jangan ragu untuk bertanya.
