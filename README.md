Monty Hall
    
    private fun isSwitchingBeneficial(): Boolean {
    
    //Initializes an array of "doors", with none containing a prize, then placing a prize behind a random door
    val prizes = arrayOf(false, false, false).apply { this[Random.nextInt(0, 3)] = true }
    
    //Choosing a door at random
    val chosenIndex = Random.nextInt(0, 3)
    
    //Showing a random "losing" door, making sure that it was not chosen.
    val shownIndex = prizes.indices.first { !prizes[it] && it != chosenIndex }
    
    //Return true if the changing doors would have been beneficial.
    return prizes[prizes.indices.first { it != shownIndex && it != chosenIndex }]
    }

Fibonacci

    fun fibonacci(length: Int) = Array(length) { 0 }.apply {
        for (i in 1 until length) this[i] = if (i == 1) i else this[i - 1] + this[i - 2]
    }

Birthday Math Problem

    fun birthdayProblem(people: Int): Double {
        var odds = 1.00
        for (i in 0 until people) odds *= (365.00 - i) / 365.00
        //Current odds are multiplied that nobody in the room as the same birthday as any other person
        //So the numerator decreases by one with each additional person, to correlate with the amount of unoccupied days
        return 1.00 - odds
    }
