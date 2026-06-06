def good_sum(N, A):
    stack = []
    total = 0

    for num in A:
        if num >= 0:
            stack.append(num)
            total += num
        else:
            abs_num = abs(num)
            sum_removed = 0
            while stack and sum_removed < abs_num:
                removed = stack.pop()
                sum_removed += removed
                total -= removed
            
            stack.append(abs_num)
            total += abs_num

    return total




def main():
    import sys
    input = sys.stdin.read
    data = input().strip().split()
    
    N = int(data[0])  # First input is the integer N
    A = list(map(int, data[1:]))  # Remaining input is the array of integers
    
    # Call user logic function and print the output
    result = good_sum(N, A)
    print(result)

if __name__ == "__main__":
    main()
