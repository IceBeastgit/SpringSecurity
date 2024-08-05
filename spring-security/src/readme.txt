 @Bean
    SecurityFilterChain web(HttpSecurity http) throws Exception {
        http
                .authorizeHttpRequests((authorize) -> authorize
                        .requestMatchers("/**").hasRole("ADMIN")
                        .anyRequest().authenticated()
                ).formLogin(withDefaults());

        return http.build();
    }
    ----------------------------------------------------------------------

