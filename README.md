// Do Przeklejenia

@Composable
fun LoginScreen() {
    // Define the gradient background
    val gradient = Brush.linearGradient(
        listOf(Color(0xFF11998E), Color(0xFF38EF7D))
    )

    Box(
        modifier = Modifier
            .fillMaxSize()
            .background(gradient)
            .padding(16.dp),
        contentAlignment = Alignment.Center
    ) {
        Column(
            horizontalAlignment = Alignment.CenterHorizontally
        ) {
            // Icon/Image
            Icon(
                imageVector = Icons.Default.AccountCircle,
                contentDescription = "Account",
                modifier = Modifier.size(160.dp),
                tint = Color.White
            )

            Spacer(modifier = Modifier.height(20.dp))

            // Email TextField
            TextField(
                value = "",
                onValueChange = {},
                label = { Text("Email", color = Color.White) },
                modifier = Modifier
                    .fillMaxWidth()
                    .background(Color.Transparent, RoundedCornerShape(24.dp)),
                textStyle = LocalTextStyle.current.copy(color = Color.White, fontSize = 20.sp),
                visualTransformation = VisualTransformation.None,
                singleLine = true,
                colors = TextFieldDefaults.textFieldColors(
                    textColor = Color.White,
                    backgroundColor = Color.Transparent,
                    focusedIndicatorColor = Color.White,
                    unfocusedIndicatorColor = Color.Transparent
                ),
                placeholder = { Text("Email", color = Color.White) }
            )

            Spacer(modifier = Modifier.height(20.dp))

            // Password TextField
            TextField(
                value = "",
                onValueChange = {},
                label = { Text("Password", color = Color.White) },
                modifier = Modifier
                    .fillMaxWidth()
                    .background(Color.Transparent, RoundedCornerShape(24.dp)),
                textStyle = LocalTextStyle.current.copy(color = Color.White, fontSize = 20.sp),
                visualTransformation = PasswordVisualTransformation(),
                singleLine = true,
                colors = TextFieldDefaults.textFieldColors(
                    textColor = Color.White,
                    backgroundColor = Color.Transparent,
                    focusedIndicatorColor = Color.White,
                    unfocusedIndicatorColor = Color.Transparent
                ),
                placeholder = { Text("Password", color = Color.White) }
            )

            Spacer(modifier = Modifier.height(20.dp))

            // Login Button
            Button(
                onClick = { /* Handle login */ },
                modifier = Modifier
                    .fillMaxWidth()
                    .padding(10.dp),
                colors = ButtonDefaults.buttonColors(
                    backgroundColor = Color.White,
                    contentColor = Color(0xFF11998E)
                ),
                shape = RoundedCornerShape(24.dp)
            ) {
                Text("Login", fontSize = 20.sp)
            }

            Spacer(modifier = Modifier.height(20.dp))

            // OR Text
            Text(
                text = "OR",
                color = Color.White,
                fontSize = 18.sp,
                fontWeight = FontWeight.Bold
            )

            Spacer(modifier = Modifier.height(20.dp))

            // Social Media Icons
            Row(
                horizontalArrangement = Arrangement.Center,
                modifier = Modifier.fillMaxWidth()
            ) {
                // Google Icon
                Icon(
                    painter = painterResource(id = R.drawable.google),  // Replace with your resource ID
                    contentDescription = "Google",
                    modifier = Modifier
                        .size(44.dp)
                        .padding(16.dp)
                        .clickable { /* Handle Google login */ }
                )

                // Meta/Facebook Icon
                Icon(
                    painter = painterResource(id = R.drawable.meta),  // Replace with your resource ID
                    contentDescription = "Meta",
                    modifier = Modifier
                        .size(48.dp)
                        .padding(16.dp)
                        .clickable { /* Handle Meta login */ }
                )
            }
        }
