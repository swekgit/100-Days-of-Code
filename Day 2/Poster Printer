import sys

def can_print_sequence(n, s):
    i = 0
    while i < n:
        # Ignore 'W' as it does not affect the result
        if s[i] == 'W':
            i += 1
            continue
        
        # Find the segment of contiguous B's and R's
        j = i
        has_B = has_R = False
        
        while j < n and s[j] != 'W':
            if s[j] == 'B':
                has_B = True
            if s[j] == 'R':
                has_R = True
            j += 1
        
        # If the segment has only one type (either all B or all R), it's invalid
        if not (has_B and has_R):
            return "NO"
        
        # Move to the next segment
        i = j
    
    return "YES"

# Read input
input = sys.stdin.read
data = input().split()

# Read number of test cases
T = int(data[0])
index = 1
results = []

for _ in range(T):
    N = int(data[index])  # Read N
    S = data[index + 1]   # Read string
    index += 2
    
    # Process and store result
    results.append(can_print_sequence(N, S))

# Print all results at once (optimized for large inputs)
sys.stdout.write("\n".join(results) + "\n")
