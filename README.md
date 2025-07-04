# mean_var_std.py
# mean_var_std.py
import numpy as np

def calculate(lst):
    # Check if the input list has exactly 9 elements
    if len(lst) != 9:
        raise ValueError("List must contain nine numbers.")
    
    # Convert list to 3x3 numpy array
    arr = np.array(lst).reshape(3, 3)
    
    # Calculate statistics
    # Axis 0: columns, Axis 1: rows, None: flattened
    calculations = {
        'mean': [
            np.mean(arr, axis=0).tolist(),  # column means
            np.mean(arr, axis=1).tolist(),  # row means
            np.mean(arr).item()            # flattened mean
        ],
        'variance': [
            np.var(arr, axis=0).tolist(),  # column variances
            np.var(arr, axis=1).tolist(),  # row variances
            np.var(arr).item()            # flattened variance
        ],
        'standard deviation': [
            np.std(arr, axis=0).tolist(),  # column std
            np.std(arr, axis=1).tolist(),  # row std
            np.std(arr).item()            # flattened std
        ],
        'max': [
            np.max(arr, axis=0).tolist(),  # column max
            np.max(arr, axis=1).tolist(),  # row max
            np.max(arr).item()            # flattened max
        ],
        'min': [
            np.min(arr, axis=0).tolist(),  # column min
            np.min(arr, axis=1).tolist(),  # row min
            np.min(arr).item()            # flattened min
        ],
        'sum': [
            np.sum(arr, axis=0).tolist(),  # column sums
            np.sum(arr, axis=1).tolist(),  # row sums
            np.sum(arr).item()            # flattened sum
        ]
    }
    
    return calculations
