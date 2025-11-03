# simple_code.py
# A simple Python script for a Stage 0 HackBio bioinformatics task.
# This script calculates the GC content of a given DNA sequence.

def calculate_gc_content(dna_sequence):
    """
    Calculates the GC content (percentage of G and C bases) of a DNA sequence.

    Args:
        dna_sequence (str): A string representing the DNA sequence.

    Returns:
        float: The GC content as a percentage, or 0.0 if the sequence is empty.
    """
    # Ensure the sequence is in uppercase for consistent counting
    dna_sequence = dna_sequence.upper()
    
    # Count the occurrences of 'G' and 'C'
    g_count = dna_sequence.count('G')
    c_count = dna_sequence.count('C')
    
    # Get the total length of the sequence
    total_length = len(dna_sequence)
    
    # Prevent division by zero if the sequence is empty
    if total_length == 0:
        return 0.0
        
    # Calculate the GC percentage
    gc_percentage = ((g_count + c_count) / total_length) * 100
    
    return gc_percentage

# --- Main part of the script ---

# 1. personal details
name = "Faith Omondi"
email = "faithanyangoomondi@gmail.com"
slack_username = "@faith"
course = "single-cell sequencing"

# 2. Define the DNA sequence to be analyzed
# This is the coding sequence for the human insulin gene.
# The sequence is provided as a multi-line string, so we'll clean it.
uncleaned_sequence = """ATGGCCCTGTGGATGCGCCTCCTGCCCCTGCTGGCGCTGCTGGCCCTCTGGGG
ACCTGACCCAGCCGCAGCCTTTGTGAACCAACACCTGTGCGGCTCACACCTGGT
GGAAGCTCTCTACCTAGTGTGCGGGGAACGAGGCTTCTTCTACACACCCAAGAC
CCGCCGGGAGGCAGAGGACCTGCAGGTGGGGCAGGTGGAGCTGGGCGGGGGCC
CTGGTGCAGGCAGCCTGCAGCCCTTGCCCGAGCTCTACCTGCTGTGCAACTCC
TACGGGTGGGCCTACGTGGACAGCCAGGCTGGCCTCGACTCC"""

# 3. Clean the sequence
# We must remove the newline characters (\n) and any spaces (just in case)
# so the length and counts are accurate.
cleaned_insulin_sequence = uncleaned_sequence.replace("\n", "").replace(" ", "")

# 4. Calculate the GC content
gc_content = calculate_gc_content(cleaned_insulin_sequence)

# 5. Print the results in a clean format
print(f"--- HackBio Stage 0 Task ---")
print(f"Name: {name}")
print(f"Email: {email}")
print(f"Slack Username: {slack_username}")
print(f"course: {course}")
print("---------------------------------")
print(f"DNA Sequence (Human Insulin Gene, 330bp): {cleaned_insulin_sequence}")
print(f"GC Content: {gc_content:.2f}%")

