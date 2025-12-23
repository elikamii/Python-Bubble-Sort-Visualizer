#def bubble_sort(arr, reverse=False):
    """
    Optimized Bubble Sort algorithm.
    :param reverse: If True, sorts in descending order.
    """
    n = len(arr)
    for i in range(n):
        swapped = False # Optimization flag
        for j in range(0, n - i - 1):
            # Check condition based on 'reverse' parameter
            condition = arr[j] < arr[j + 1] if reverse else arr[j] > arr[j + 1]
            
            if condition:
                arr[j], arr[j + 1] = arr[j + 1], arr[j]
                swapped = True
        
        # If no two elements were swapped by inner loop, then break
        if not swapped:
            break
    return arr

# Test cases
numbers = [64, 34, 25, 12, 22, 11, 90]

print(f"Ascending:  {bubble_sort(numbers.copy())}")
print(f"Descending: {bubble_sort(numbers.copy(), reverse=True)}")
